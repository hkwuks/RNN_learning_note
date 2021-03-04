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

- 可以自定义$h_{t}$的更新策略

  ![image.png](RNN.assets/20210302181516-qdkdisg-image.png)

- $h_{t}$的更新函数

  ![image.png](RNN.assets/20210302181721-088hiir-image.png)

### 2、训练

![image.png](RNN.assets/20210302213027-bleqimq-image.png)

![image.png](RNN.assets/20210302214545-qgkx9hi-image.png)

### 3、梯度爆炸和梯度弥散

由于RNN的梯度中包含$W_{R}$的幂，多层RNN网络容易出现梯度爆炸或梯度弥散的问题。

#### Gradient Clipping 缓解梯度爆炸

通过限制梯度的极端值大小来缓解梯度爆炸的问题。

![image.png](RNN.assets/20210303151923-m1bt4y9-image.png)

#### LSTM解决梯度弥散

![image-20210303172605871](RNN.assets/image-20210303172605871.png)

- **Forget gate**

  **对C~t-1~进行处理，保留部分记忆**

  ![image-20210303184131989](RNN.assets/image-20210303184131989.png)

- **Input gate**

  - **对输入数据进行处理，保留部分数据**

  ![image-20210303193206622](RNN.assets/image-20210303193206622.png)

  - **将处理后的$C_{t-1}$与处理后的输入相加，生成$C_{t}$**

![image-20210303193749413](RNN.assets/image-20210303193749413.png)

- **Output gate**

  **对输出进行处理，保留部分数据，输出$h_{t}$**

  ![image-20210303193841411](RNN.assets/image-20210303193841411.png)

![image-20210303220120214](RNN.assets/image-20210303220120214.png)

- **三个门组合逻辑**

  ![image-20210303220633365](RNN.assets/image-20210303220633365.png)

- **LSTM如何解决梯度弥散**

  **避免了$W_{R}^{k}$出现**

  

  ![image-20210303223409973](RNN.assets/image-20210303223409973.png)

