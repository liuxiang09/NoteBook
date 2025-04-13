```
LISAForCausalLM(
  (model): LisaModel(
    (embed_tokens): Embedding(32004, 4096, padding_idx=0)
    (layers): ModuleList(
      (0): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (1): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (2): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (3): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (4): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (5): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (6): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (7): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (8): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (9): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (10): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (11): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (12): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (13): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (14): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (15): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (16): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (17): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (18): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (19): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (20): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (21): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (22): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (23): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (24): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (25): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (26): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (27): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (28): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (29): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (30): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
      (31): LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (k_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (v_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (o_proj): Linear(in_features=4096, out_features=4096, bias=False)
          (rotary_emb): LlamaRotaryEmbedding()
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (up_proj): Linear(in_features=4096, out_features=11008, bias=False)
          (down_proj): Linear(in_features=11008, out_features=4096, bias=False)
          (act_fn): SiLUActivation()
        )
        (input_layernorm): LlamaRMSNorm()
        (post_attention_layernorm): LlamaRMSNorm()
      )
    )
    (norm): LlamaRMSNorm()
    (vision_tower): CLIPVisionTower()
    (mm_projector): Linear(in_features=1024, out_features=4096, bias=True)
    (visual_model): Sam(
      (image_encoder): ImageEncoderViT(
        (patch_embed): PatchEmbed(
          (proj): Conv2d(3, 1280, kernel_size=(16, 16), stride=(16, 16))
        )
        (blocks): ModuleList(
          (0): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (1): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (2): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (3): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (4): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (5): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (6): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (7): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (8): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (9): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (10): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (11): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (12): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (13): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (14): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (15): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (16): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (17): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (18): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (19): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (20): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (21): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (22): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (23): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (24): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (25): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (26): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (27): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (28): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (29): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (30): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
          (31): Block(
            (norm1): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (attn): Attention(
              (qkv): Linear(in_features=1280, out_features=3840, bias=True)
              (proj): Linear(in_features=1280, out_features=1280, bias=True)
            )
            (norm2): LayerNorm((1280,), eps=1e-06, elementwise_affine=True)
            (mlp): MLPBlock(
              (lin1): Linear(in_features=1280, out_features=5120, bias=True)
              (lin2): Linear(in_features=5120, out_features=1280, bias=True)
              (act): GELU(approximate='none')
            )
          )
        )
        (neck): Sequential(
          (0): Conv2d(1280, 256, kernel_size=(1, 1), stride=(1, 1), bias=False)
          (1): LayerNorm2d()
          (2): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False)
          (3): LayerNorm2d()
        )
      )
      (prompt_encoder): PromptEncoder(
        (pe_layer): PositionEmbeddingRandom()
        (point_embeddings): ModuleList(
          (0): Embedding(1, 256)
          (1): Embedding(1, 256)
          (2): Embedding(1, 256)
          (3): Embedding(1, 256)
        )
        (not_a_point_embed): Embedding(1, 256)
        (mask_downscaling): Sequential(
          (0): Conv2d(1, 4, kernel_size=(2, 2), stride=(2, 2))
          (1): LayerNorm2d()
          (2): GELU(approximate='none')
          (3): Conv2d(4, 16, kernel_size=(2, 2), stride=(2, 2))
          (4): LayerNorm2d()
          (5): GELU(approximate='none')
          (6): Conv2d(16, 256, kernel_size=(1, 1), stride=(1, 1))
        )
        (no_mask_embed): Embedding(1, 256)
      )
      (mask_decoder): MaskDecoder(
        (transformer): TwoWayTransformer(
          (layers): ModuleList(
            (0): TwoWayAttentionBlock(
              (self_attn): Attention(
                (q_proj): Linear(in_features=256, out_features=256, bias=True)
                (k_proj): Linear(in_features=256, out_features=256, bias=True)
                (v_proj): Linear(in_features=256, out_features=256, bias=True)
                (out_proj): Linear(in_features=256, out_features=256, bias=True)
              )
              (norm1): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (cross_attn_token_to_image): Attention(
                (q_proj): Linear(in_features=256, out_features=128, bias=True)
                (k_proj): Linear(in_features=256, out_features=128, bias=True)
                (v_proj): Linear(in_features=256, out_features=128, bias=True)
                (out_proj): Linear(in_features=128, out_features=256, bias=True)
              )
              (norm2): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (mlp): MLPBlock(
                (lin1): Linear(in_features=256, out_features=2048, bias=True)
                (lin2): Linear(in_features=2048, out_features=256, bias=True)
                (act): ReLU()
              )
              (norm3): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (norm4): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (cross_attn_image_to_token): Attention(
                (q_proj): Linear(in_features=256, out_features=128, bias=True)
                (k_proj): Linear(in_features=256, out_features=128, bias=True)
                (v_proj): Linear(in_features=256, out_features=128, bias=True)
                (out_proj): Linear(in_features=128, out_features=256, bias=True)
              )
            )
            (1): TwoWayAttentionBlock(
              (self_attn): Attention(
                (q_proj): Linear(in_features=256, out_features=256, bias=True)
                (k_proj): Linear(in_features=256, out_features=256, bias=True)
                (v_proj): Linear(in_features=256, out_features=256, bias=True)
                (out_proj): Linear(in_features=256, out_features=256, bias=True)
              )
              (norm1): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (cross_attn_token_to_image): Attention(
                (q_proj): Linear(in_features=256, out_features=128, bias=True)
                (k_proj): Linear(in_features=256, out_features=128, bias=True)
                (v_proj): Linear(in_features=256, out_features=128, bias=True)
                (out_proj): Linear(in_features=128, out_features=256, bias=True)
              )
              (norm2): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (mlp): MLPBlock(
                (lin1): Linear(in_features=256, out_features=2048, bias=True)
                (lin2): Linear(in_features=2048, out_features=256, bias=True)
                (act): ReLU()
              )
              (norm3): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (norm4): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
              (cross_attn_image_to_token): Attention(
                (q_proj): Linear(in_features=256, out_features=128, bias=True)
                (k_proj): Linear(in_features=256, out_features=128, bias=True)
                (v_proj): Linear(in_features=256, out_features=128, bias=True)
                (out_proj): Linear(in_features=128, out_features=256, bias=True)
              )
            )
          )
          (final_attn_token_to_image): Attention(
            (q_proj): Linear(in_features=256, out_features=128, bias=True)
            (k_proj): Linear(in_features=256, out_features=128, bias=True)
            (v_proj): Linear(in_features=256, out_features=128, bias=True)
            (out_proj): Linear(in_features=128, out_features=256, bias=True)
          )
          (norm_final_attn): LayerNorm((256,), eps=1e-05, elementwise_affine=True)
        )
        (iou_token): Embedding(1, 256)
        (mask_tokens): Embedding(4, 256)
        (output_upscaling): Sequential(
          (0): ConvTranspose2d(256, 64, kernel_size=(2, 2), stride=(2, 2))
          (1): LayerNorm2d()
          (2): GELU(approximate='none')
          (3): ConvTranspose2d(64, 32, kernel_size=(2, 2), stride=(2, 2))
          (4): GELU(approximate='none')
        )
        (output_hypernetworks_mlps): ModuleList(
          (0): MLP(
            (layers): ModuleList(
              (0): Linear(in_features=256, out_features=256, bias=True)
              (1): Linear(in_features=256, out_features=256, bias=True)
              (2): Linear(in_features=256, out_features=32, bias=True)
            )
          )
          (1): MLP(
            (layers): ModuleList(
              (0): Linear(in_features=256, out_features=256, bias=True)
              (1): Linear(in_features=256, out_features=256, bias=True)
              (2): Linear(in_features=256, out_features=32, bias=True)
            )
          )
          (2): MLP(
            (layers): ModuleList(
              (0): Linear(in_features=256, out_features=256, bias=True)
              (1): Linear(in_features=256, out_features=256, bias=True)
              (2): Linear(in_features=256, out_features=32, bias=True)
            )
          )
          (3): MLP(
            (layers): ModuleList(
              (0): Linear(in_features=256, out_features=256, bias=True)
              (1): Linear(in_features=256, out_features=256, bias=True)
              (2): Linear(in_features=256, out_features=32, bias=True)
            )
          )
        )
        (iou_prediction_head): MLP(
          (layers): ModuleList(
            (0): Linear(in_features=256, out_features=256, bias=True)
            (1): Linear(in_features=256, out_features=256, bias=True)
            (2): Linear(in_features=256, out_features=4, bias=True)
          )
        )
      )
    )
    (text_hidden_fcs): ModuleList(
      (0): Sequential(
        (0): Linear(in_features=4096, out_features=4096, bias=True)
        (1): ReLU(inplace=True)
        (2): Linear(in_features=4096, out_features=256, bias=True)
        (3): Dropout(p=0.0, inplace=False)
      )
    )
  )
  (lm_head): Linear(in_features=4096, out_features=32004, bias=False)
)
```

