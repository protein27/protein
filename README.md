# protein

## 代码结构（有问题查pytorch的documentation，版本为0.4.1）

### /27 主要代码

Atlas.py：定义数据集。继承Dataset，用dataloader封装后可以方便地调用图片和标签

utils.py：F1_soft计算F1 score，fit_val计算最适合验证集的阈值

train.py：很简单很常规的训练代码，可以看一下pytorch的训练流程

model.py：定义了用的模型，用的是预训练的resnet18

config.yml：设置训练的参数

### /Analysis 用于分析结果，计算confusion matrix

### /Test.py

test.py：用验证集上得到的阈值，对测试集进行预测，保存的结果submission.csv可以直接提交


## 2018/11/22

任务分配：配置服务器环境（陈）；跑通baseline（勇）；混淆矩阵（年）；结果分析（俞）；设定阈值提交结果（天）；搭建resnet18（张）

## code
<https://www.kaggle.com/rejpalcz/cnn-128x128x4-keras-from-scratch-lb-0-328>


## information
![4channels](4channels.JPG)
images by [Jonathan Schnabel](https://www.kaggle.com/jschnab/exploring-the-human-protein-atlas-images)

green: protein  
red: microtubules  
blue: nucleus  
yellow: endoplasmic reticulum  


![distribution](distribution.png)

0  Nucleoplasm  
1  Nuclear membrane  
2  Nucleoli  
3  Nucleoli fibrillar center  
4  Nuclear speckles  
5  Nuclear bodies  
6  Endoplasmic reticulum  
7  Golgi apparatus  
8  Peroxisomes  
9  Endosomes  
10  Lysosomes  
11  Intermediate filaments  
12  Actin filaments  
13  Focal adhesion sites  
14  Microtubules  
15  Microtubule ends  
16  Cytokinetic bridge  
17  Mitotic spindle  
18  Microtubule organizing center  
19  Centrosome  
20  Lipid droplets  
21  Plasma membrane  
22  Cell junctions  
23  Mitochondria  
24  Aggresome  
25  Cytosol  
26  Cytoplasmic bodies   
27  Rods & rings  
