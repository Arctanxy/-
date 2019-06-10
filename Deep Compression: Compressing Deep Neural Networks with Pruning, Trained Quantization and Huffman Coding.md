# DEEP COMPRESSION: COMPRESSING DEEP NEURAL NETWORKS WITH PRUNING, TRAINED QUANTIZATION AND HUFFMAN CODING

**摘要：**

通过三步走（剪枝、量化、哈夫曼编码）的方式实现神经网络压缩及加速

可以再不降低精度的情况下，将内存量减少35-49倍

剪枝方法为在线剪枝，即在训练过程中学习每个连接的重要性，从而减去不必要的连接

剪枝能将连接数减少9-13倍

量化操作会将数据从32位量化到5位

可以在无精度损失的情况下，将AlexNet从240MB压缩到6.9MB，VGG16从552MB压缩到11.3MB。

每层网络运算速度提升3到4倍，能效提高3到7倍。

**正文：**

1. 剪枝

LeCun在1989年就提出过使用剪枝来降低神经网络的复杂度以减少过拟合。

在训练过程中，得到的小于某个阈值的权重会被移除，然后用剩下的稀疏权重继续训练，训练后继续移除数值过小的权重。

稀疏矩阵采用行压缩或者列压缩形式存储

*剪枝的阈值是该层layer的标准差乘以一个超参数*

> 论文解读及github源码：https://blog.csdn.net/zijin0802034/article/details/53982812


剪枝过程：

![剪枝过程](img/prune.jpg)
