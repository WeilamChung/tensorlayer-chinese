<!--<div align="center">
	<div class="TensorFlow">
  <img src="https://www.tensorflow.org/images/tf_logo_transp.png" style=": left; margin-left: 5px; margin-bottom: 5px;"><br><br>
   </div>
   <div class="TensorLayer">
    <img src="https://www.tensorflow.org/images/tf_logo_transp.png" style=": right; margin-left: 5px; margin-bottom: 5px;">
    </div>
</div>
-->
<a href="http://github.com/zsdonghao/tensorlayer">
<div align="center">
	<img src="img/img_tensorlayer.png" width="30%" height="30%"/>
</div>
</a>


# TensorLayer: 面向研究人员和工程师的深度学习和强化学习库  

TensorLayer 是为研究人员和工程师设计的一款基于[Google TensorFlow](https://www.tensorflow.org)开发的深度学习与强化学习库。 
它提供高级别的（Higher-Level）深度学习API，这样不仅可以加快研究人员的实验速度,也能够减少工程师在实际开发当中的重复工作。
TensorLayer非常易于修改和扩展，这使它可以同时用于机器学习的研究与应用。此外，TensorLayer 提供了大量示例和教程来帮助初学者理解深度学习，并提供大量的官方例子程序方便开发者快速找到适合自己项目的例子。

阅读TensorLayer Readthedocs 文档您不仅可以学会如何使用这个库，也会了解不同类型的神经网络、深度学习、强化学习，还有自然语言处理等内容。此外，TensorLayer的Tutorial包含了所有TensorFlow官方深度学习教程的模块化实现，因此你可以对照TensorFlow深度学习教程来学习[[英文]](https://www.tensorflow.org/versions/master/tutorials/index.html)[[极客学院中文翻译]](http://wiki.jikexueyuan.com/project/tensorflow-zh/)。

不过，与其它基于TensorFlow开发的傻瓜式API不同，TensorLayer需要使用者有基本的神经网络知识。了解TensorFlow的基础，可以让你非常熟练地使用它。

🌞🌞🌞 我们建议你在[Github](http://github.com/zsdonghao/tensorlayer) 上star和watch[官方项目](http://github.com/zsdonghao/tensorlayer)，这样当官方有更新时，你会立即知道。本文档为[官方RTD文档](https://github.com/zsdonghao/tensorlayer)的翻译版，更新速度会比英文原版慢，若你的英文还行，我们建议你直接阅读[官方RTD文档](https://github.com/zsdonghao/tensorlayer)

❤️❤️❤️ TensorLayer首批开发者包括中国人，我们承诺将一直支持中国社区

-


TensorLayer 在兼顾 TensorFlow 的灵活性的同时，又能为使用者提供合适的操作粒度来建立和训练神经网络。TensorLayer的开发遵循以下几个原则：

- 透明性：用户可以直接使用 TensorFlow 的方法来操作所有有的训练，迭代，初始化过程，我们鼓励用户尽可能多的在TensorLayer中使用TensorFlow的方法，利用TensorFlow所提供的便利。
- 张量：张量是一个可用来表示在一些向量、标量和其他张量之间的线性关系的多线性函数。TensorFlow 使用这种数据结构来表示神经网络所需要的数据。
- 教程：TensorLayer提供了大量的连贯教程，让用户可以循序渐进的学习使用TensorLayer和深度学习了解，教程的内容覆盖了 Dropout, DropConnect, Denoising Autoencoder, LSTM, CNN 等等。
- TPU：Tensor Process Unit 是为了针对 TensorFlow 深度学习打造的定制化ASIC芯片。
- 分布式：TensorFlow 默认支持分布式系统。
- 兼容性：单层网络的建立被抽象成正则化，成本和每一层的输出，方便与其他基于TensorFlow的库协作。
- 简洁：易于使用，扩展与修改，以便在研究和工程中使用。
- 高速：在GPU的支持下运行速度与纯TensorFlow脚本速度一致。简洁但不牺牲性能。

让我们在 [overview](#overview) 中看看TensorLayer强大的功能吧!!!




-

####🇨🇳为了促进华人开发者的交流速度，我们建立了多种交流渠道，您可把微信号发送到 haodong_cs@163.com 申请加入。

####🇹🇭เราขอเรียนเชิญนักพัฒนาคนไทยทุกคนที่สนใจจะเข้าร่วมทีมพัฒนา TensorLayer ติดต่อสอบถามรายละเอียดเพิ่มเติมได้ที่ haodong_cs@163.com

####🇬🇧If you are in London, we can discuss face to face.

-

# Readme 目录
0. [库目录 Library Structure](#库目录)
0. [概述 Overview](#概述)
0. [如何修改 Easy to Modify](#如何修改)
0. [安装步骤 Installation](#安装步骤)
0. [参与开发 Ways to Contribute](#参与开发)
0. [英文在线文档](http://tensorlayer.readthedocs.io/)
0. [下载英文 PDF](https://media.readthedocs.org/pdf/tensorlayer/latest/tensorlayer.pdf)
0. [下载英文 Epub](http://readthedocs.org/projects/tensorlayer/downloads/epub/latest/)
0. [下载英文 HTML](http://readthedocs.org/projects/tensorlayer/downloads/htmlzip/latest/)
0. [中文在线文档](http://tensorlayercn.readthedocs.io/)
0. [下载中文 PDF](https://media.readthedocs.org/pdf/tensorlayercn/latest/tensorlayercn.pdf)
0. [下载中文 Epub](http://readthedocs.org/projects/tensorlayercn/downloads/epub/latest/)
0. [下载中文 HTML](http://readthedocs.org/projects/tensorlayercn/downloads/htmlzip/latest/)

--
# 库目录

[TensorLayer 官方 Github](https://github.com/zsdonghao/tensorlayer)的目录如下。

```
<folder>
├── tensorlayer  		<--- library source code
│
├── setup.py			<--- use ‘python setup.py install’ or ‘pip install . -e‘, to install
├── docs 				<--- readthedocs folder
│   └── _build          <--- not included in the remote repo but can be generated in `docs` using `make html`
│   	 └──html
│			 └──index.html <--- homepage of the documentation
├── tutorials_*.py	 	<--- tutorials include NLP, DL, RL etc.
├── .. 
```
--
# 概述

如果您了解更多关于深度学习，增强学习和自然语言处理的内容，请移步*[Read the Docs 英文版](http://tensorlayer.readthedocs.io/en/latest/)*或*[Read the Docs 中文版](http://tensorlayercn.readthedocs.io)*。您也可以下载这些文档以便您在本地阅读。

0. [多层神经网络 Fully Connected Network](#)
0. [卷积神经网络 Convolutional Neural Network](#)
0. [递归神经网络 Recurrent Neural Network](#)
0. [强化学习 Reinforcement Learning](#)
0. [损失函数 Cost Function](#)

### *多层神经网络*

TensorLayer 提供了大量最新的(state-of-the-art)神经网络层,他们包括Dropout, DropConnect, ResNet, Pre-train 等等。

**<font color="grey"> 占位符 (placeholder): </font>**

所有的占位符(placeholder)和变量(variable)都可以使用 TensorFlow 的方法进行初始化。如果您想了解更多关于变量，占位符初始化的细节，请阅读 *[tensorflow-placeholder](https://www.tensorflow.org/versions/master/api_docs/python/io_ops.html#placeholder)*, *[tensorflow-variables](https://www.tensorflow.org/versions/master/how_tos/variables/index.html)* and *[tensorflow-math](https://www.tensorflow.org/versions/r0.9/api_docs/python/math_ops.html)*

```python
# 在MNIST实例中，每一张图片的尺寸是28x28，有784个像素点，即784个输入。
import tensorflow as tf
import tensorlayer as tl
x = tf.placeholder(tf.float32, shape=[None, 784], name='x')
y_ = tf.placeholder(tf.int64, shape=[None, ], name='y_')
```

**<font color="grey"> Dropout+Relu: </font>**

```python
# 定义神经网络
network = tl.layers.InputLayer(x, name='input_layer')
network = tl.layers.DropoutLayer(network, keep=0.8, name='drop1')
network = tl.layers.DenseLayer(network, n_units=800, act = tf.nn.relu, name='relu1')
network = tl.layers.DropoutLayer(network, keep=0.5, name='drop2')
network = tl.layers.DenseLayer(network, n_units=800, act = tf.nn.relu, name='relu2')
network = tl.layers.DropoutLayer(network, keep=0.5, name='drop3')
network = tl.layers.DenseLayer(network, n_units=10, act = tl.activation.identity, name='output_layer')
# 开始训练
...
```
**<font color="grey"> 普通稀疏自编码器 Vanilla Sparse Autoencoder: </font>**


```python
# 定义网络
network = tl.layers.InputLayer(x, name='input_layer')
network = tl.layers.DenseLayer(network, n_units=196, act = tf.nn.sigmoid, name='sigmoid1')
recon_layer1 = tl.layers.ReconLayer(network, x_recon=x, n_units=784, act = tf.nn.sigmoid, name='recon_layer1')
# 开始预训练
sess.run(tf.initialize_all_variables())
recon_layer1.pretrain(sess, x=x, X_train=X_train, X_val=X_val, denoise_name=None, n_epoch=200, batch_size=128, print_freq=10, save=True, save_name='w1pre_')
...
```
**<font color="grey"> 去噪自编码器 Denoising Autoencoder: </font>**


```python
# 定义网络
network = tl.layers.InputLayer(x, name='input_layer')
network = tl.layers.DropoutLayer(network, keep=0.5, name='denoising1')   
network = tl.layers.DenseLayer(network, n_units=196, act = tf.nn.relu, name='relu1')
recon_layer1 = tl.layers.ReconLayer(network, x_recon=x, n_units=784, act = tf.nn.softplus, name='recon_layer1')
# 开始预训练
sess.run(tf.initialize_all_variables())
recon_layer1.pretrain(sess, x=x, X_train=X_train, X_val=X_val, denoise_name='denoising1', n_epoch=200, batch_size=128, print_freq=10, save=True, save_name='w1pre_')
...
```

**<font color="grey"> 堆栈式去噪自编码器 Stacked Denoising Autoencoder: </font>**

```python
# 定义网络
network = tl.layers.InputLayer(x, name='input_layer')
# denoise layer for Autoencoders
network = tl.layers.DropoutLayer(network, keep=0.5, name='denoising1')
# 第一层
network = tl.layers.DropoutLayer(network, keep=0.8, name='drop1')
network = tl.layers.DenseLayer(network, n_units=800, act = tf.nn.relu, name='relu1')
x_recon1 = network.outputs
recon_layer1 = tl.layers.ReconLayer(network, x_recon=x, n_units=784, act = tf.nn.softplus, name='recon_layer1')
# 第二层
network = tl.layers.DropoutLayer(network, keep=0.5, name='drop2')
network = tl.layers.DenseLayer(network, n_units=800, act = tf.nn.relu, name='relu2')
recon_layer2 = tl.layers.ReconLayer(network, x_recon=x_recon1, n_units=800, act = tf.nn.softplus, name='recon_layer2')
# 的三层
network = tl.layers.DropoutLayer(network, keep=0.5, name='drop3')
network = tl.layers.DenseLayer(network, n_units=10, act = tl.activation.identity, name='output_layer')

sess.run(tf.initialize_all_variables())

# 显示模型参数信息
network.print_params()

# 开始预训练 Layer 1
recon_layer1.pretrain(sess, x=x, X_train=X_train, X_val=X_val, denoise_name='denoising1', n_epoch=100, batch_size=128, print_freq=10, save=True, save_name='w1pre_')
# 开始预训练 Layer 2
recon_layer2.pretrain(sess, x=x, X_train=X_train, X_val=X_val, denoise_name='denoising1', n_epoch=100, batch_size=128, print_freq=10, save=False)
# 开始训练, 微调 fine-tune
...
```

### *卷积神经网络 Convolutional Neural Network*

在卷积神经网络中，图片集可以被表示成一个四维的矩阵来作为输入而不是一个1维向量，即 [None, 28, 28, 1]代表[batchsize, height, width, channels]。将batchsize设置为None的意思是数据可以以任意的batchsize来填入占位符。

```python
x = tf.placeholder(tf.float32, shape=[None, 28, 28, 1])
y_ = tf.placeholder(tf.int64, shape=[None,])
```

**<font color="grey"> CNNs + MLP: </font>**

以下代码定义了一个2层卷积神经网络,每一层之后都是一个全连接(fully-connected)网络:
```python
network = tl.layers.InputLayer(x, name='input_layer')
network = tl.layers.Conv2dLayer(network,
                        act = tf.nn.relu,
                        shape = [5, 5, 1, 32],  # 32 features for each 5x5 patch
                        strides=[1, 1, 1, 1],
                        padding='SAME',
                        name ='cnn_layer1')     # output: (?, 28, 28, 32)
network = tl.layers.Pool2dLayer(network,
                        ksize=[1, 2, 2, 1],
                        strides=[1, 2, 2, 1],
                        padding='SAME',
                        pool = tf.nn.max_pool,
                        name ='pool_layer1',)   # output: (?, 14, 14, 32)
network = tl.layers.Conv2dLayer(network,
                        act = tf.nn.relu,
                        shape = [5, 5, 32, 64], # 64 features for each 5x5 patch
                        strides=[1, 1, 1, 1],
                        padding='SAME',
                        name ='cnn_layer2')     # output: (?, 14, 14, 64)
network = tl.layers.Pool2dLayer(network,
                        ksize=[1, 2, 2, 1],
                        strides=[1, 2, 2, 1],
                        padding='SAME',
                        pool = tf.nn.max_pool,
                        name ='pool_layer2',)   # output: (?, 7, 7, 64)
network = tl.layers.FlattenLayer(network, name='flatten_layer')                                # output: (?, 3136)
network = tl.layers.DropoutLayer(network, keep=0.5, name='drop1')                              # output: (?, 3136)
network = tl.layers.DenseLayer(network, n_units=256, act = tf.nn.relu, name='relu1')           # output: (?, 256)
network = tl.layers.DropoutLayer(network, keep=0.5, name='drop2')                              # output: (?, 256)
network = tl.layers.DenseLayer(network, n_units=10, act = tl.activation.identity, name='output_layer')    # output: (?, 10)
```
如果您希望了解更多的功能，请移步 *[Read the Docs](http://tensorlayer.readthedocs.io/en/latest/)*。

### *递归神经网络 Recurrent Neural Network*

**<font color="grey"> LSTM: </font>** 

如果您想了解LSTM,请移步*[Understand LSTM](http://tensorlayer.readthedocs.io/en/latest/user/tutorial.html#run-the-ptb-example)*。

### *增强学习 Reinforcement Learning*

为了使您能够更加深入的了解，我们向您推荐这篇博客 *[Deep Reinforcement Learning: Pong from Pixels](http://karpathy.github.io/2016/05/31/rl/)* 和这篇文章 *[Playing Atari with Deep Reinforcement Learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)*。如果您想亲自试试增强学习，我们建议您使用 *[OpenAI Gym](https://github.com/openai/gym)* 作为benchmark。

**<font color="grey"> Pong Game: </font>**

Atari Pong Game is a single agent example. *[Pong from Pixels](http://karpathy.github.io/2016/05/31/rl/)* using 130 lines of Python only *[(Code link)](https://gist.github.com/karpathy/a4166c7fe253700972fcbc77e4ea32c5)* can be reimplemented as follow.

雅达利(Atari)的乒乓球游戏是一个 single agent example, *[Pong from Pixels](http://karpathy.github.io/2016/05/31/rl/)* 只用了130行python代码，这些代码可以像以下这样重新实现。

```python
# 策略网络(policy network)
network = tl.layers.InputLayer(x, name='input_layer')
network = tl.layers.DenseLayer(network, n_units= H , act = tf.nn.relu, name='relu_layer')
network = tl.layers.DenseLayer(network, n_units= 1 , act = tf.nn.sigmoid, name='output_layer')
```

如果您想了解更多关于增强学习的内容，请您移步*[Policy Gradient](http://tensorlayer.readthedocs.io/en/latest/user/tutorial.html#understand-reinforcement-learning)*。


### *损失函数 Cost Function*

TensorLayer 为用户提供了非常简便的途径来创建用户自己的损失函数(cost finction)。比如以下这个多层感知机(multi-layer percptron)的例子。

```python
network = tl.InputLayer(x, name='input_layer')
network = tl.DropoutLayer(network, keep=0.8, name='drop1')
network = tl.DenseLayer(network, n_units=800, act = tf.nn.relu, name='relu1')
network = tl.DropoutLayer(network, keep=0.5, name='drop2')
network = tl.DenseLayer(network, n_units=800, act = tf.nn.relu, name='relu2')
network = tl.DropoutLayer(network, keep=0.5, name='drop3')
network = tl.DenseLayer(network, n_units=10, act = tl.activation.identity, name='output_layer')
```

**<font color="grey"> 参数正则化 Regularization of Weights: </font>**

在初始化变量之后，我们可以使用**<font color="grey">network.print_params()</font>**方法来输出网络的参数信息。

```python
sess.run(tf.initialize_all_variables())
network.print_params()
>> param 0: (784, 800) (mean: -0.000000, median: 0.000004 std: 0.035524)
>> param 1: (800,) (mean: 0.000000, median: 0.000000 std: 0.000000)
>> param 2: (800, 800) (mean: 0.000029, median: 0.000031 std: 0.035378)
>> param 3: (800,) (mean: 0.000000, median: 0.000000 std: 0.000000)
>> param 4: (800, 10) (mean: 0.000673, median: 0.000763 std: 0.049373)
>> param 5: (10,) (mean: 0.000000, median: 0.000000 std: 0.000000)
>> num of params: 1276810
```
!!!
**<font color="grey">network.outputs</font>**是模型的输出，之后我们就可以像下面这样定义交叉熵。除此之外，**<font color="grey">network.all_params</font>** 包含了模型的所有参数。就以下这个例子来说**<font color="grey">network.all_params</font>** = [W1, b1, W2, b2, Wout, bout] 根据用*<font color="grey">network.print_params()</font>**方法显示的参数0,1, ... ,5。然后对于 W1 和 W2 的最大范数就可以通过以下代码来实现。
!!!
```python
y = network.outputs
cross_entropy = tf.reduce_mean(tf.nn.sparse_softmax_cross_entropy_with_logits(y, y_))
cost = cross_entropy
cost = cost + tl.cost.maxnorm_regularizer(1.0)(network.all_params[0]) + tl.cost.maxnorm_regularizer(1.0)(network.all_params[2])
```
除外，所有TensorFlow的正则项(regularizers)都可以被用于TensorLayer,比如 **<font color="grey">tf.contrib.layers.l2_regularizer</font>**。

**<font color="grey">启发函数输出的正则化 Regularization of Activation Outputs: </font>**


！！！
**<font color="grey">network.print_layers()</font>**方法会按顺序打印每一层的输出。**<font color="grey">network.all_layers</font>**
包含了不同层的所有输出。比方说，如果用户希望使用 L1 罚项作为第一层启发函数的罚项，用户只需要把 **<font color="grey">tf.contrib.layers.l2_regularizer(lambda_l1)(network.all_layers[1])</font>** 加到损失函数。
！！！

```python
network.print_layers()
>> layer 0: Tensor("dropout/mul_1:0", shape=(?, 784), dtype=float32)
>> layer 1: Tensor("Relu:0", shape=(?, 800), dtype=float32)
>> layer 2: Tensor("dropout_1/mul_1:0", shape=(?, 800), dtype=float32)
>> layer 3: Tensor("Relu_1:0", shape=(?, 800), dtype=float32)
>> layer 4: Tensor("dropout_2/mul_1:0", shape=(?, 800), dtype=float32)
>> layer 5: Tensor("add_2:0", shape=(?, 10), dtype=float32)
```
如果希望了解更多，请移步*[Read the Docs](http://tensorlayer.readthedocs.io/en/latest/)*.

# 如何修改
**<font color="grey">修改预训练行为 Modifying Pre-train Behaviour: </font>**

逐层贪婪的预训练(Greedy layer-wise pretrain)对于深度神经网络的初始化是非常重要的。根据不同的应用和模型，测量逐层贪婪预训练的方法也各不相同。

比方说，*[Vanilla Sparse Autoencoder](http://deeplearning.stanford.edu/wiki/index.php/Autoencoders_and_Sparsity)* 的预训练是通过Kullback–Leibler散度(KL divergence)来实现的(请看以下代码)。但是，对于*[Deep Rectifier Network](http://www.jmlr.org/proceedings/papers/v15/glorot11a/glorot11a.pdf)* 权值矩阵的稀疏行是通过对输出的启发函数使用 L1 范式来实现的。

```python
# 普通稀疏自编码器 Vanilla Sparse Autoencoder
beta = 4
rho = 0.15
p_hat = tf.reduce_mean(activation_out, reduction_indices = 0)
KLD = beta * tf.reduce_sum( rho * tf.log(tf.div(rho, p_hat)) + (1- rho) * tf.log((1- rho)/ (tf.sub(float(1), p_hat))) )
```

For this reason, TensorLayer provides a simple way to modify or design your own pre-train metrice. For Autoencoder, TensorLayer uses **ReconLayer.*__*init__()** to define the reconstruction layer and cost function, to define your own cost function, just simply modify the **self.cost** in **ReconLayer.*__*init__()**. To creat your own cost expression please read *[Tensorflow Math](https://www.tensorflow.org/versions/master/api_docs/python/math_ops.html)*. By default, **ReconLayer** only updates the weights and biases of previous 1 layer by using **self.train_params = self.all _params[-4:]**, where the 4 parameters are [W_encoder, b_encoder, W_decoder, b_decoder]. If you want to update the parameters of previous 2 layers, simply modify **[-4:]** to **[-6:]**.


```python    
ReconLayer.__init__(...):
    ...
    self.train_params = self.all_params[-4:]
    ...
	self.cost = mse + L1_a + L2_w
```

**<font color="grey">使用自定义的正则项 Adding Customized Regularizer: </font>**

请查看 tensorlayer/cost.py


# 安装步骤

**<font color="grey"> 安装 TensorFlow：</font>**

请预先安装TensorFlow，它的版本需要 >= 0.8： *[Tensorflow 安装指南（英文版）](https://www.tensorflow.org/versions/r0.9/get_started/os_setup.html)*。

**<font color="grey"> 设置 GPU：</font>**

TensorFlow GPU版需要你先安装 CUDA 和 cuDNN：

*[CUDA, CuDNN 安装指南（英文版）](https://www.tensorflow.org/versions/master/get_started/os_setup.html#optional-install-cuda-gpus-on-linux)*

*[CUDA 下载](https://developer.nvidia.com/cuda-downloads)*

*[cuDNN 下载](https://developer.nvidia.com/cudnn)*

**<font color="grey"> 安装 TensorLayer：</font>**

你可以跟着下面的步骤安装TensorLayer，详细请参考 [Read the Docs](http://tensorlayercn.readthedocs.io/zh/latest/user/installation.html)。

```python
python setup.py install
or
pip install . -e
```


# 参与开发

TensorLayer 始于帝国理工大学Data Science Institute的内部项目，主要用于帮助科研工作者测试他们的一些想法和算法。然而现在我们鼓励世界各地的研究者发布自己的方法用以促进和加快机器学习的进一步发展。

如果你可以证明你的算法比现有的方法更快更好更有效，我们将会把它加入到TensorLayer中。请同时提供测试用的文件和具体的算法描述。

# 网上文档

0. [英文在线文档](http://tensorlayer.readthedocs.io/)
0. [中文在线文档](http://tensorlayercn.readthedocs.io/)

如果您想在本地生成这些文档，也可以跟着下面的步骤：

```shell
cd docs
make html
```

# 下载文档

0. [下载英文 PDF](https://media.readthedocs.org/pdf/tensorlayer/latest/tensorlayer.pdf)
0. [下载英文 Epub](http://readthedocs.org/projects/tensorlayer/downloads/epub/latest/)
0. [下载英文 HTML](http://readthedocs.org/projects/tensorlayer/downloads/htmlzip/latest/)
0. [下载中文 PDF](https://media.readthedocs.org/pdf/tensorlayercn/latest/tensorlayercn.pdf)
0. [下载中文 Epub](http://readthedocs.org/projects/tensorlayercn/downloads/epub/latest/)
0. [下载中文 HTML](http://readthedocs.org/projects/tensorlayercn/downloads/htmlzip/latest/)
