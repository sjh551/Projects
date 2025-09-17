# CIFAR-10 Classification
A entry-level classification task: set up a simple network, CIFAR-10 dataset
# Dataset description
CIFAR-10 is a standard dataset used for image classification, containing natural images of 10 categories such as airplane, cars, birds, cats, etc.
Download at https://www.cs.toronto.edu/~kriz/cifar.html
![10 categories](https://github.com/sjh551/Projects/blob/e9fb46d31ab76ef78a9a4a9cc5aa4a5333ce3899/Classification/code/CIFAR10/image.png)\
该数据集的基本信息见表1，data_batch_1 ~ data_batch_5为训练集，test_batch为测试集，batches.meta文件提供标签名称（如label_names[0] = "airplane"）
每个文件（如data_batch_1）包含10000张图像，存储为一个字典。里面包含data与labels。
* data的形状为 (10000, 3072) 的uint8数组。每行代表一张图像，按RGB通道顺序，存储方式：前1024个值为红色通道，中间1024为绿色，后1024为蓝色。
* labels: 包含10000个整数标签（0-9），对应10个类别。  
  
**Table 1 basic information about CIFAR-10**  
  
| 属性 | 描述 |
|---|---|
|总样本量|60,000张 (50k训练 + 10k测试)|
|类别数|10|
|图像尺寸|32×32像素 RGB彩色|
|文件结构|6个二进制batch文件 + meta文件|  

在官方网页下载数据集后解压并组织成如下目录形式：
```
├──dataset
│   └──cifar-10-python
│       └── cifar-10-batches-py
│            ├── batches.meta
│            ├── data_batch_1
│            ├── data_batch_2
│            ├── data_batch_3
│            ├── data_batch_4
│            ├── data_batch_5
│            ├── readme.html
│            └── test_batch
├──code
```
# Set up a Model
