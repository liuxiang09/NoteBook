[TOC]



### Keras框架

### TensorFlow框架

### 全连接神经网络（Fully Connected Neural Network）

> 其他类型神经网络的基本，最基础的原理都是由反向传播而来

<img src="https://pic3.zhimg.com/v2-8d0d03d122da50d62f9ec5567883a4ba_b.jpg" alt="深度学习开端｜全连接神经网络- 知乎" style="zoom:67%;" />

分为输入层，隐藏层，输出层，反向传播是将Loss传回去，目的是消除Loss。

**归一化：**通过一个f（x）将每次输出限制在0-1之间，以作为下一层合理的输入。



现在我们要找到这个三维图像的最低点：



<img src="https://pic4.zhimg.com/v2-43dbaa592eba61fa6a21051c56c451cf_b.jpg" alt="深度学习开端｜全连接神经网络- 知乎" style="zoom: 67%;" />

想象我们要从山上以**最快**的速度到达山下，那么在每一点的时候都需要找到那个偏导数最大的位置，因为这个时候下降的是最快的，那么这个最陡峭的切线就叫做**梯度**。
每走一步我们的坐标都会更新，这样循环往复，直到到达山地，或超过某个阈值，或达到一定的迭代次数，停止训练，这样找到的（w， b）就是我们要求的解。
整个下降的过程叫做：**梯度下降求解法**

还有一个关于学习率的说明：通常来说，我们可以根据以往的经验或阅读书本来选择一个合适的学习率（没错，学习率是自己随意设置），当然也可以根据直觉直接选（蒙）一个学习率。不同的学习率对于Loss的作用不尽相同，不论是过高还是过低都不会有很好的训练效果。

<img src="https://raw.githubusercontent.com/terrifyzhao/terrifyzhao.github.io/master/assets/img/2019-05-23-%E5%AD%A6%E4%B9%A0%E7%8E%87Learning%20rate/pic1.jpg" alt="一文看懂学习率Learning Rate，从入门到CLR_爱编程真是太好了的博客-CSDN博客_初始学习率" style="zoom:50%;" />

#### 小结：

全连接神经网络作为最基础的神经网络，相对与CNN，RNN等神经网络，它们的原理和训练过程都是差不多的，无非就是网络结构变了。另外当钻研理论到一定程度后，在设计一个新的网络结构时，此时对原理的熟练程度直接决定着所设计网络结构的优劣。

**缺点：**我们知道为了求解损失Loss列出了关于（w，b）的方程，我们使用了梯度下降的方法。简单来说就是沿着最陡峭的地方，不断往下走，一直走到山底。	为此我们必须要通过求偏导的方式来得到每一点的梯度，这时就必须要用到链式法则。重点来了，网络层次越深，偏导连乘的次数也就越多，所付出的计算代价也就越大。网络结构越复杂，整个网络收敛得也就越慢，特别是针对图像这些冗余信息特别多的输入，如果用全连接神经网络去训练，可以说是一场计算灾难。这时候，**卷积神经网络**就诞生了。

#### 优化器

为了缓解基于梯度下降法在数据量增多时导致的速度变慢问题，有人为梯度下降算法做出了优化，这便是优化器。

##### 随机梯度下降（SGD）

梯度下降法每次训练都使用全部样本，然而这些计算是冗余的，因为每次训练都用同样的样本去计算。SGD每次只选一个样本用来更新梯度，学习速度非常快，并且支持对新的数据进行在线更新。

为此付出的代价是，SGD由于每次选择样本的随机性，会有些许波动，有时会从一个点突然跳到另外一个点。走出的路线会相当曲折。

<img src="https://seanlee97.github.io/images/posts/gradient_descent/05.png" alt="常用的梯度下降优化算法| 明天探索者" style="zoom: 67%;" />

##### Momentum

Momentum是**动量**，用来解决SGD的波动性，从而抑制SGD的振荡。当随机梯度下降拥有的动量，那么就相当于具有了惯性，那么即使随机也会受惯性限制，不可能随便跳来跳去。

![动量梯度下降法Momentum - Welcome to AI World](https://raw.githubusercontent.com/terrifyzhao/terrifyzhao.github.io/master/assets/img/2018-02-14-%E5%8A%A8%E9%87%8F%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95Momentum/momentum6.png)

##### RMSprop

[理解 RMSprop——更快的神经网络学习](https://towardsdatascience.com/understanding-rmsprop-faster-neural-network-learning-62e116fcf29a)

![img](https://miro.medium.com/max/775/1*Y2KPVGrVX9MQkeI8Yjy59Q.gif)

<img src="https://miro.medium.com/max/775/0*o9jCrrX4umP7cTBA" alt="img" style="zoom: 80%;" />

##### Adaptive Moment Estimation（Adam）

相当于Momentum和RMSprop的结合，拥有的两者的优点，因此在很多优秀的论文中都可以看到它被用作神经网络的优化器。所以，如果不知道怎么选用优化器，那就选择Adam吧！

#### 学习率

梯度下降更新权值公式如下：
$$
\omega _{t+1} = \omega _{t} - \alpha \cdot grandient
$$
整个训练过程其实就是梯度下降更新权值的过程，学习率的作用可以通过上述公式和这幅图来理解，对于凸函数，大的学习率可能会在学习过程中跳过全局极值点，小的学习率虽然速度慢但是最终能收敛到全局极值点，求得最优解。

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRpNws-S-NGGZ0wMPh9C_Aq-b0Tx8uo6IFlcA&usqp=CAU" alt="从浅到深全面理解梯度下降：原理，类型与优势-ATYUN" style="zoom:150%;" />



但是对于非凸函数，使用小的学习率很可能最终收敛到局部的最小值而不是全局最小值，从而得不到最优解。

<img src="data:image/png;base64,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" alt="学习率— PaddleEdu documentation" style="zoom:200%;" />

那么到底应该怎样选择学习率呢？目前业界还没有很好的方法，只能通过自己调参数使得学习率调到最优.

### 卷积神经网络

















