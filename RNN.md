# RNN基础

## 一、Encoding

### 1.One-hot

- 维度高，占用空间

![image.png](RNN.assets/20210301215956-1ti9fs7-image.png)

### 2.语义相关性 semantic similarity

![image.png](RNN.assets/20210301220521-1ksfujk-image.png)

- 计算方式

  ![image.png](RNN.assets/20210301222143-fsp4v4t-image.png)
- 通常使用的编码方式

  - word2vec
  - GloVe

## 二、RNN网络

### 1、网络结构

![image.png](RNN.assets/20210302180838-e9bdfq9-image.png)

- 可以自定义h~t~的更新策略

  ![image.png](RNN.assets/20210302181516-qdkdisg-image.png)

- h~t~的更新函数

  ![image.png](RNN.assets/20210302181721-088hiir-image.png)

### 2、训练

![image.png](RNN.assets/20210302213027-bleqimq-image.png)

![image.png](RNN.assets/20210302214545-qgkx9hi-image.png)

### 3、梯度爆炸和梯度弥散

由于RNN的梯度中包含W~R~的幂，多层RNN网络容易出现梯度爆炸或梯度弥散的问题。

#### Gradient Clipping 缓解梯度爆炸

通过限制梯度的极端值大小来缓解梯度爆炸的问题。

![image.png](RNN.assets/20210303151923-m1bt4y9-image.png)

####