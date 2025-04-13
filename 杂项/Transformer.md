```python
import math
import torch
import numpy as np
import torch.nn as nn
import torch.optim as optim
import torch.utils.data as Data


# 数据预处理以及参数设置


# S: Symbol that shows starting of decoding input
# E: Symbol that shows starting of decoding output
# P: Symbol that will fill in blank sequence if current batch data size is short than time steps
# 'P' 就是填充项，我们要统一句子长度，但并不是每一个句子都有那么长，所以不够的用'P'填充。
sentences = [
        #enc_input              dec_input               dec_output
        ['ich mochte ein bier P','S i want a beer .','i want a beer . E'],
        ['ich mochte ein cola P','S i want a coke .','i want a coke . E']
]

#Padding Should be Zero
src_vocab = {'P':0, 'ich':1, 'mochte':2, 'ein':3, 'bier':4, 'cola':5}
src_vocab_size = len(src_vocab)

tgt_vocab = {'P':0, 'i':1, 'want':2, 'a':3, 'beer':4, 'coke':5, 'S':6, 'E':7, '.':8}
tgt_vocab_size = len(tgt_vocab)
idx2word = {i:w for i, w in enumerate(tgt_vocab)}

# print(idx2word)
print(sentences[0][0].split())
# src_len就是源句子的长度是5，tgt_len就是目标句子的长度是6。
src_len = 5
tgt_len = 6

# make_data()的作用是将原来的单词转化为对应在词汇表中的数字，并生成enc_inputs,dec_inputs,dec_outputs这几个数据，务必要记住他们的形状。
def make_data(sentences):
    enc_inputs, dec_inputs, dec_outputs = [], [], []
    for i in range(len(sentences)):
        enc_input = [[src_vocab[n] for n in sentences[i][0].split()]]   # [[1, 2, 3, 4, 0], [1, 2, 3, 5, 0]]
        dec_input = [[tgt_vocab[n] for n in sentences[i][1].split()]]   # [[6, 1, 2, 3, 4, 8], [6, 1, 2, 3, 5, 8]]
        dec_output = [[tgt_vocab[n] for n in sentences[i][2].split()]]  # [[1, 2, 3, 4, 8, 7], [1, 2, 3, 5, 8, 7]]

        enc_inputs.extend(enc_input)
        dec_inputs.extend(dec_input)
        dec_outputs.extend(dec_output)

    return torch.LongTensor(enc_inputs), torch.LongTensor(dec_inputs), torch.LongTensor(dec_outputs)
    

enc_inputs, dec_inputs, dec_outputs = make_data(sentences)
print(len(enc_inputs))



class MyDataSet(Data.Dataset):
    def __init__(self, enc_inputs, dec_inputs, dec_outputs):
        super().__init__()
        self.enc_inputs = enc_inputs    # 编码器输入
        self.dec_inputs = dec_inputs    # 解码器输入
        self.dec_outputs = dec_outputs  # 解码器输出

        # 通常添加长度校验
        assert len(enc_inputs) == len(dec_inputs) == len(dec_outputs), "所有输入和输出的长度必须一致"
        
    # 返回样本的数目
    def __len__(self):
        return self.enc_inputs.shape[0]
    
    def __getitem__(self, idx):
        return self.enc_inputs[idx], self.dec_inputs[idx], self.dec_outputs[idx]

mydataset = MyDataSet(enc_inputs, dec_inputs, dec_outputs)
loader = Data.DataLoader(mydataset, 2, shuffle=True)



# 模型参数
"""
d_model：词嵌入的维度（= 位置嵌入维度）
d_ff：Feed Forward中两层linear中间的过渡维度（512 -> 2048 -> 512）
d_k、d_v：分别是K 、V的维度，其中Q和K相等的就省略了
n_layers：EncoderLayer的数量，也就是blocks的数量
n_heads：Multi-Head Attention 的头数
"""
# Transformer Parameters
d_model = 512   # Embedding Size (= Positional Size)
d_ff = 2048     # Feed Forward(512 -> 2048 -> 512)
d_k = d_v = 64  # dimension of qkv
n_layers = 6    # number of encoder-layer (= n blocks)
n_heads = 8     # number of heads in Multi-Head Attention


# Position Encoding
# 位置编码模块的过程是这样的，在他之前对输入序列已经进行了词嵌入，所以该模块输入的是word_embedding,形状为：[batch_size, src_len, d_model]，
# 而位置编码是写死的，在模块初始化的时候生成，将pos_embedding + word_embedding,然后输出，输出的形状：[batch_size,src_len, d_model ]，
# 得到了经过word_embedding 和 pos_embedding 的输入表示。
class PositionalEncoding(nn.Module):
    def __init__(self, d_model, dropout=0.1, max_len=5000):
        """
        位置嵌入层初始化
        Args:
            d_model: 嵌入维度（必须与词嵌入维度相同）
            dropout: dropout概率
            max_len: 支持的最大序列长度
            pe: 位置编码矩阵
            div_term: 用于计算正弦和余弦函数的频率
        """
        super().__init__()                          # 调用父类nn.Module的初始化
        self.dropout = nn.Dropout(p=dropout)        # 初始化dropout层
        # 初始化位置编码矩阵 [max_len, d_model]
        pe = torch.zeros(max_len, d_model)          # 创建全零矩阵，用于存储位置编码
        position = torch.arange(0, max_len, dtype=torch.float).unsqueeze(1)     # 生成位置序列 [0, 1, 2, ..., max_len-1]，并转换为列向量 [max_len, 1]
        # 计算除数项div_term，用于控制正弦/余弦函数的频率:
        # exp(2i * (-log(10000)/d_model))，其中i是维度索引
        # 这里d_model是嵌入维度，10000是原始Transformer论文中的常数
        div_term = torch.exp(torch.arange(0, d_model, 2).float()*(-math.log(10000.0) / d_model))
        pe[:,0::2] = torch.sin(position * div_term) # 计算偶数维度的位置编码（使用正弦函数）
        pe[:,1::2] = torch.cos(position * div_term) # 计算奇数维度的位置编码（使用余弦函数）
        # 调整pe的形状，增加一个batch维度 [1, max_len, d_model]
        pe = pe.unsqueeze(0).transpose(0, 1)        # 变形为[max_len, 1, d_model]
        self.register_buffer('pe', pe)              # 将pe注册为缓冲区（不参与训练但会保存到模型状态中）


    def forward(self, x):
        """
        前向传播
        Args:
            x: 输入张量 [seq_len, batch_size, d_model]
        Returns:
            添加位置编码后的输出 [seq_len, batch_size, d_model]
        """
        # pe[:x.size(0), :]操作是取出pe的前x.size(0)行，目的是裁剪pe使其与输入x的长度一致
        # 此时pe的形状为 [seq_len, 1, d_model]
        # x为[seq_len, batch_size, d_model] + [seq_len, 1, d_model]
        x = x + self.pe[:x.size(0), :]              # 利用广播机制，pe的第二维的1会广播到batch_size的大小
        print(self.pe[:x.size(0), :].shape)         # 打印位置编码的形状
        print(x.shape)                              # 打印添加位置编码后的输出形状       
        return self.dropout(x)                      # 返回经过dropout处理的输出




# pos_embed = PositionEncoding(d_model)
# x = torch.randn(10, 32, d_model)  # 模拟输入 [seq_len=10, batch_size=32, d_model=512]
# output = pos_embed(x)  # 输出形状不变，但已添加位置信息
# print(output.shape)  # 输出形状 [10, 32, 512]


# PadMAsk
# 这里的作用就是Mask Pad，即遮掩掉填充项，让其他单词对于填充项'P'的注意力权重几乎为0。在词表中填充项'P'的索引为0，所以我们用0来表示填充项。
def get_attn_pad_mask(seq_q, seq_k):
    """
    获取填充掩码
    Args:
        seq_q: 查询序列 [batch_size, src_len]
        seq_k: 键序列 [batch_size, src_len]
    Returns:
        填充掩码 [batch_size, src_len, src_len]
    """
    batch_size, len_q = seq_q.size()  # 获取查询序列的批大小和长度
    batch_size, len_k = seq_k.size()  # 获取键序列的批大小和长度
    # eq(zero) is Pad token
    pad_attn_mask = seq_k.eq(0).unsqueeze(1)  # 创建填充掩码 [batch_size, 1, len_k]
    return pad_attn_mask.expand(batch_size, len_q, len_k)  # 扩展掩码 [batch_size, len_q, len_k]

# # 测试填充掩码
# enc_inputs, dec_inputs, dec_outputs = make_data(sentences)
# pad_mask = get_attn_pad_mask(enc_inputs, dec_inputs)
# print(pad_mask.shape)  # 输出形状 [batch_size, src_len, src_len]
# print(pad_mask)  # 打印填充掩码


# Subsequent Mask
# Subsequent Mask是为了在解码时屏蔽掉未来的信息，确保模型只能看到当前和之前的位置信息。
def get_attn_subsequence_mask(seq):
    '''
    获取后续掩码
    Args:
        seq: 输入序列 [batch_size, tgt_len]
    Returns:
        后续掩码 [batch_size, tgt_len, tgt_len]
    '''
    attn_shape = [seq.size(0), seq.size(1), seq.size(1)]            # [batch_size, tgt_len, tgt_len]
    subsequence_mask = np.triu(np.ones(attn_shape), k=1)            # 创建上三角矩阵，k=1表示对角线以上的元素为1
    subsequence_mask = torch.from_numpy(subsequence_mask).byte()    # 转换为PyTorch张量，并转换为byte类型
    return subsequence_mask

# # 测试后续掩码
# _, dec_inputs, dec_outputs = make_data(sentences)
# subsequence_mask = get_attn_subsequence_mask(dec_inputs)
# print(subsequence_mask.shape)  # 输出形状 [batch_size, tgt_len, tgt_len]
# print(subsequence_mask)  # 打印后续掩码


# ScaledDotProductAttention
# 输入序列 → 嵌入 → 线性投影 → 拆分为 Q/K/V → 缩放点积注意力 → 输出
class ScaledDotProductAttention(nn.Module):
    def __init__(self):
        """
        缩放点积注意力机制
        """
        super().__init__()

    def forward(self, Q, K, V, attn_mask):
        """
        前向传播
        Args:
            Q: 查询张量 [batch_size, n_heads, len_q, d_k]
            K: 键张量 [batch_size, n_heads, len_k, d_k]
            V: 值张量 [batch_size, n_heads, len_v, d_v]
            attn_mask: 注意力掩码 [batch_size, n_heads, len_q, len_k]
        Returns:
            输出张量 [batch_size, n_heads, len_q, d_v]，注意力权重 [batch_size, n_heads, len_q, len_k]
        """
        # 计算缩放点积注意力
        scores = torch.matmul(Q, K.transpose(-1, -2)) / np.sqrt(d_k)  # 计算注意力分数 scores : [batch_size, n_heads, len_q, len_k]
        scores.masked_fill_(attn_mask, -1e9) # 将掩码位置的分数设置为负无穷大
        # 在最后一个维度上应用softmax函数，将分数转化为概率分布
        attn = nn.Softmax(dim=-1)(scores)    # 计算注意力权重 [batch_size, n_heads, len_q, len_k]
        context = torch.matmul(attn, V)      # 计算上下文向量 [batch_size, n_heads, len_q, d_v]
        return context, attn                 # 返回上下文向量和注意力权重
    

# MultiHeadAttention
class MultiHeadAttention(nn.Module):
    def __init__(self):
        super().__init__()
        self.W_Q = nn.Linear(d_model, d_k * n_heads, bias=False)    # 一次性做8个heads的qkv映射
        self.W_K = nn.Linear(d_model, d_k * n_heads, bias=False)
        self.W_V = nn.Linear(d_model, d_v * n_heads, bias=False)
        self.fc = nn.Linear(d_v * n_heads, d_model, bias=False)     # 最后输出的线性映射

    def forward(self, input_Q, input_K, input_V, attn_mask):
        """
        前向传播
        Args:
            input_Q: 查询张量    [batch_size, len_q, d_model]
            input_K: 键张量      [batch_size, len_k, d_model]
            input_V: 值张量      [batch_size, len_v, d_model]
            attn_mask: 注意力掩码 [batch_size, len_q, len_k]
        Returns:
            输出张量 [batch_size, len_q, d_model]，注意力权重 [batch_size, n_heads, len_q, len_k]
        """
        residual, batch_size = input_Q, input_Q.size(0)  # 获取输入的残差连接和批大小
        #(B, S, D) -proj->(B, S, D_new) -split-> (B, S, H, W) -trans-> (B, H, S, W)
        Q = self.W_Q(input_Q).view(batch_size, -1, n_heads, d_k).transpose(1, 2)  # [batch_size, n_heads, len_q, d_k]
        K = self.W_K(input_K).view(batch_size, -1, n_heads, d_k).transpose(1, 2)
        V = self.W_V(input_V).view(batch_size, -1, n_heads, d_v).transpose(1, 2)

        attn_mask = attn_mask.unsqueeze(1).repeat(1, n_heads, 1, 1)  # 扩展掩码维度 [batch_size, n_heads, len_q, len_k]

        #context: [batch_size, n_heads, len_q, d_v], attn: [batch_size, n_heads, len_q, len_k]
        context, attn = ScaledDotProductAttention()(Q, K, V, attn_mask)
        context = context.transpose(1,2).reshape(batch_size, -1, n_heads * d_v) # context:[batch_size,len_q, n_heads*d_v]
        output = self.fc(context) # output:[batch_size, len_q, d_model]
        return nn.LayerNorm(d_model).cuda()(output + residual), attn
    

# FeedForward Layer
# FeedForward Layer是一个两层的全连接网络，通常用于Transformer中的每个编码器和解码器层。
# 两个线性层，中间用ReLu()函数激活，最后进行residual和LayerNorm操作
class PoswiseFeedForwardNet(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc = nn.Sequential(nn.Linear(d_model, d_ff, bias=False),   # 第一层线性变换
                                nn.ReLU(),                              # RELU激活函数
                                nn.Linear(d_ff, d_model, bias=False))   # 第二层线性变换
        
    def forward(self, inputs):
        """
        前向传播
        Args:
            inputs: 输入张量 [batch_size, len_q, d_model]
        Returns:
            输出张量 [batch_size, len_q, d_model]
        """
        residual = inputs
        output = self.fc(inputs)
        return nn.LayerNorm(d_model).cuda()(output + residual)  # 残差连接和LayerNorm
    

# Encoder Layer
# Encoder Layer是Transformer中的编码器层，包含多头注意力机制和前馈网络。
class EncoderLayer(nn.Module):
    def __init__(self):
        super().__init__()
        self.enc_self_attn = MultiHeadAttention()   # 多头自注意力机制
        self.pos_ffn = PoswiseFeedForwardNet()         # 前馈网络

    def forward(self, enc_inputs, enc_self_attn_mask):
        """
        前向传播
        Args:
            enc_inputs: 编码器输入 [batch_size, len_q, d_model]
            enc_self_attn_mask: 自注意力掩码 [batch_size, src_len, src_len]
        Returns:
            enc_outputs: 编码器输出 [batch_size, len_q, d_model]
            attn: 注意力权重 [batch_size, n_heads, src_len, src_len]
        """
        enc_outputs, attn = self.enc_self_attn(enc_inputs, enc_inputs, enc_inputs, enc_self_attn_mask)
        enc_outputs = self.pos_ffn(enc_outputs)
        return enc_outputs, attn
    
# Decoder Layer
# Decoder Layer是Transformer中的解码器层，包含多头注意力机制和前馈网络。
class DecoderLayer(nn.Module):
    def __init__(self):
        super().__init__()
        self.dec_self_attn = MultiHeadAttention()
        self.dec_enc_attn = MultiHeadAttention()    # 编码器-解码器注意力
        self.pos_ffn = PoswiseFeedForwardNet()         # 前馈网络

    def forward(self, dec_inputs, enc_outputs, dec_self_attn_mask, dec_enc_attn_mask):
        """
        前向传播
        Args:
            dec_inputs: 解码器输入 [batch_size, tgt_len, d_model]
            enc_outputs: 编码器输出 [batch_size, src_len, d_model]
            dec_self_attn_mask: 解码器自注意力掩码 [batch_size, tgt_len, tgt_len]
            dec_enc_attn_mask: 编码器-解码器注意力掩码 [batch_size, tgt_len, src_len]
        Returns:
            dec_outputs: 解码器输出 [batch_size, tgt_len, d_model]
            dec_self_attn: 解码器自注意力权重 [batch_size, n_heads, tgt_len, tgt_len]
            dec_enc_attn: 编码器-解码器注意力权重 [batch_size, n_heads, tgt_len, src_len]
        """
        dec_outputs, dec_self_attn = self.dec_self_attn(dec_inputs, dec_inputs, dec_inputs, dec_self_attn_mask)
        dec_outputs, dec_enc_attn = self.dec_enc_attn(dec_outputs, enc_outputs, enc_outputs, dec_enc_attn_mask)
        dec_outputs = self.pos_ffn(dec_outputs)
        return dec_outputs, dec_self_attn, dec_enc_attn
    
# Encoder
# Encoder是Transformer中的编码器，包含多个编码器层。
class Encoder(nn.Module):
    def __init__(self):
        super().__init__()
        self.src_emb = nn.Embedding(src_vocab_size, d_model)  # 源嵌入层
        self.pos_emb = PositionalEncoding(d_model)               # 位置嵌入层
        self.layers = nn.ModuleList([EncoderLayer() for _ in range(n_layers)])

    def forward(self, enc_inputs):
        """
        前向传播
        Args:
            enc_inputs: 编码器输入 [batch_size, src_len]
        Returns:
            enc_outputs: 编码器输出 [batch_size, src_len, d_model]
            enc_self_attn: 编码器自注意力权重 [batch_size, n_heads, src_len, src_len]
        """
        enc_outputs = self.src_emb(enc_inputs)  # [batch_size, src_len, d_model]
        enc_outputs = self.pos_emb(enc_outputs.transpose(0, 1)).transpose(0, 1)  # [batch_size, src_len, d_model]
        enc_self_attn_mask = get_attn_pad_mask(enc_inputs, enc_inputs)  # [batch_size, src_len, src_len]
        enc_self_attns = []
        for layer in self.layers:
            # enc_outputs: [batch_size, src_len, d_model] , enc_self_attn: [batch_size, n_heads, src_len, src_len]
            enc_outputs, enc_self_attn = layer(enc_outputs, enc_self_attn_mask)
            enc_self_attns.append(enc_self_attn)
        return enc_outputs, enc_self_attns
    
# Decoder
# Decoder是Transformer中的解码器，包含多个解码器层。
class Decoder(nn.Module):
    def __init__(self):
        super().__init__()
        self.tgt_emb = nn.Embedding(tgt_vocab_size, d_model)     # 目标嵌入层
        self.pos_emb = PositionalEncoding(d_model)               # 位置嵌入层
        self.layers = nn.ModuleList([DecoderLayer() for _ in range(n_layers)])

    def forward(self, dec_inputs, enc_outputs):
        """
        前向传播
        Args:
            dec_inputs: 解码器输入 [batch_size, tgt_len]
            enc_outputs: 编码器输出 [batch_size, src_len, d_model]
        Returns:
            dec_outputs: 解码器输出 [batch_size, tgt_len, d_model]
            dec_self_attns: 解码器自注意力权重 [batch_size, n_heads, tgt_len, tgt_len]
            dec_enc_attns: 编码器-解码器注意力权重 [batch_size, n_heads, tgt_len, src_len]
        """
        dec_outputs = self.tgt_emb(dec_inputs) # [batch_size, tgt_len, d_model]
        dec_outputs = self.pos_emb(dec_outputs.transpose(0, 1)).transpose(0, 1).cuda() # [batch_size, tgt_len, d_model]
        dec_self_attn_pad_mask = get_attn_pad_mask(dec_inputs, dec_inputs).cuda() # [batch_size, tgt_len, tgt_len]
        dec_self_attn_subsequence_mask = get_attn_subsequence_mask(dec_inputs).cuda() # [batch_size, tgt_len, tgt_len]
        dec_self_attn_mask = torch.gt((dec_self_attn_pad_mask + dec_self_attn_subsequence_mask), 0).cuda() # [batch_size, tgt_len, tgt_len]
 
        dec_enc_attn_mask = get_attn_pad_mask(dec_inputs, enc_inputs) # [batc_size, tgt_len, src_len]
 
        dec_self_attns, dec_enc_attns = [], []
        for layer in self.layers:
            # dec_outputs: [batch_size, tgt_len, d_model], dec_self_attn: [batch_size, n_heads, tgt_len, tgt_len], dec_enc_attn: [batch_size, h_heads, tgt_len, src_len]
            dec_outputs, dec_self_attn, dec_enc_attn = layer(dec_outputs, enc_outputs, dec_self_attn_mask, dec_enc_attn_mask)
            dec_self_attns.append(dec_self_attn)
            dec_enc_attns.append(dec_enc_attn)
        return dec_outputs, dec_self_attns, dec_enc_attns



class Transformer(nn.Module):
    def __init__(self):
        super(Transformer, self).__init__()
        self.encoder = Encoder().cuda()
        self.decoder = Decoder().cuda()
        self.projection = nn.torch.Linear(d_model, tgt_vocab_size, bias=False).cuda()
 
    def forward(self,enc_inputs,dec_inputs,dec_outputs):
        '''
        :param enc_inputs: [batch_size, src_len]
        :param dec_inputs: [batch_size, tgt_len]
        :return:
        '''
        # tensor to store decoder outputs
        # outputs = torch.zeros(batch_size, tgt_len, tgt_vocab_size).to(self.device)
 
        # enc_outputs: [batch_size, src_len, d_model], enc_self_attns: [n_layers, batch_size, n_heads, src_len, src_len]
        enc_outputs, enc_self_attns = self.encoder(enc_inputs)
        #dec_outputs: [batch_size,tgt_len, d_model],dec_self_attns: [n_layers, batch_size, n_heads, tgt_len, tgt_len],dec_enc_attn: [n_layers, batch_size, tgt_len, src_len]
        dec_outputs, dec_self_attns, dec_enc_attns = self.decoder(dec_inputs,enc_inputs, enc_outputs)
        dec_logits = self.projection(dec_outputs)
        return dec_logits.view(-1, dec_logits.size(-1)),enc_self_attns,dec_self_attns, dec_enc_attns
```

以下是Transformer模型中数据流动过程中各模块的输入输出形状变化分析，按处理顺序展示关键步骤：

---

### 1. **输入数据准备**

- `enc_inputs`: `[batch_size=2, src_len=5]` (原始编码器输入序列)
- `dec_inputs`: `[batch_size=2, tgt_len=6]` (原始解码器输入序列)

---

### 2. **编码器（Encoder）处理流程**

#### 2.1 词嵌入层 (`src_emb`)

- **输入**: `enc_inputs` `[2, 5]`
- **输出**: `[2, 5, d_model=512]`  
  （将单词索引映射为512维向量）

#### 2.2 位置编码 (`pos_emb`)

- **输入**: 嵌入后张量 `[2, 5, 512]`（需转置为 `[5, 2, 512]`）
- **输出**: `[5, 2, 512]` → 转置回 `[2, 5, 512]`  
  （添加位置信息，形状不变）

#### 2.3 自注意力掩码 (`get_attn_pad_mask`)

- **输入**: `enc_inputs` `[2, 5]`（两次）
- **输出**: `[2, 5, 5]`  
  （标记PAD位置，避免注意力计算）

#### 2.4 编码器层 (`EncoderLayer`) ×6

每层处理流程：

1. **多头自注意力** (`MultiHeadAttention`):
   - **输入**: `[2, 5, 512]`  和 `attn = [2, 5, 5]`
   - **Q/K/V投影**: 拆分为 `[2, 8 heads, 5, 64]`  
   - **输出**: `[2, 5, 512]`（残差连接+LayerNorm后）
2. **前馈网络** (`PoswiseFeedForwardNet`):
   - **输入/输出**: `[2, 5, 512]`（维度不变）

最终编码器输出：  

- `enc_outputs`: `[2, 5, 512]`  
- `enc_self_attns`: 6层注意力权重，每层 `[2, 8, 5, 5]`

---

### 3. **解码器（Decoder）处理流程**

#### 3.1 词嵌入层 (`tgt_emb`)

- **输入**: `dec_inputs` `[2, 6]`
- **输出**: `[2, 6, 512]`

#### 3.2 位置编码 (`pos_emb`)

- 同编码器，输出 `[2, 6, 512]`

#### 3.3 解码器掩码生成

1. **填充掩码** (`get_attn_pad_mask`):
   - 输出: `[2, 6, 6]`
2. **序列掩码** (`get_attn_subsequence_mask`):
   - 输出: `[2, 6, 6]`（上三角矩阵）
3. **合并掩码**: `[2, 6, 6]`（逻辑或操作）

#### 3.4 解码器层 (`DecoderLayer`) ×6

每层处理流程：

1. **自注意力**:
   - **输入**: `[2, 6, 512]` → 输出 `[2, 6, 512]`
   - 注意力权重: `[2, 8, 6, 6]`
2. **编码器-解码器注意力**:
   - **输入**: 解码器输出 `[2, 6, 512]` + 编码器输出 `[2, 5, 512]`
   - **输出**: `[2, 6, 512]`
   - 注意力权重: `[2, 8, 6, 5]`
3. **前馈网络**: 保持 `[2, 6, 512]`

最终解码器输出：  

- `dec_outputs`: `[2, 6, 512]`  
- 注意力权重: 各6层 `[2, 8, 6, 6]` 和 `[2, 8, 6, 5]`

---

### 4. **输出投影层 (`projection`)**

- **输入**: `dec_outputs` `[2, 6, 512]`
- **输出**: `[2, 6, tgt_vocab_size=9]` → 展平为 `[12, 9]`  
  （12=2×6，每个时间步预测词汇表概率）

---

### 关键形状总结

| 模块         | 输入形状       | 输出形状            |
| ------------ | -------------- | ------------------- |
| 编码器词嵌入 | [2, 5]         | [2, 5, 512]         |
| 解码器词嵌入 | [2, 6]         | [2, 6, 512]         |
| 编码器输出   | [2, 5]（初始） | [2, 5, 512]（最终） |
| 解码器输出   | [2, 6]（初始） | [2, 6, 512]（最终） |
| 投影层       | [2, 6, 512]    | [12, 9]             |

注意：所有残差连接和LayerNorm均不改变形状。多头注意力的内部拆分/合并操作已简化为最终输出形状。