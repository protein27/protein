# 人类蛋白质数据库图像分类 – 概述
对人类细胞中的蛋白质亚细胞结构进行分类
## 描述
在本比赛中，参赛者需要建立对复杂蛋白质微观图像分类的模型。人类蛋白质数据库（HPA）将利用这些模型，与他们的显微系统结合，构建从高流量图像中识别蛋白质位置的工具。
蛋白质是人类细胞的功能承担者，担负着许多生命活动的功能。传统上，蛋白质的分类局限在一种或几种细胞的单一模式。而要想充分理解人类细胞的复杂性，模型必须能够对人类各种不同细胞的复杂混合模式中进行分类。
细胞中蛋白质的可视化是生物医学研究的常用手段，这些细胞可能带来药学研究的重大突破。高流量显微技术使得这些图像高速生成，远远超过人工分析的速度。因此现在迫切需要自动对生物医学图像进行分析的方法，以加快对人类细胞和疾病的理解。

*Nature Methods有兴趣发表关于本挑战的结果与方法的论文。人类蛋白质数据库的团队希望邀请前几名的队伍作为共同作者。*

*前几名的队伍将能够参与特殊奖金的竞赛。关于特殊奖金和Nature Methods共同作者的信息将在主要比赛结束后发布。*

### 致谢

人类蛋白质数据库是瑞典的研究团队，旨在描绘人类蛋白质在细胞、组织、器官中的分布。所有数据资源均向人类蛋白质组的研究人员开放。人类蛋白质数据库在最近的论文中已经阐明公众科学和人工智能在描述人类蛋白质在图像中位置的前景，但现在的结果还未达到专家级别的程度。

## 评分

提交结果将根据Macro-F1宏平均的方法评分。

### 提交文件

对于测试集中的每个Id，应预测Target标签变量的分类，参考格式见数据页。注意每个样本可能对应多个标签。

文件应包含表头，格式如下：

```
Id,Predicted  
00008af0-bad0-11e8-b2b8-ac1f6b6435d0,0 1  
0000a892-bacf-11e8-b2b8-ac1f6b6435d0,2 3
0006faa6-bac7-11e8-b2b7-ac1f6b6435d0,0  
0008baca-bad7-11e8-b2b9-ac1f6b6435d0,0  
000cce7e-bad4-11e8-b2b8-ac1f6b6435d0,0  
00109f6a-bac8-11e8-b2b7-ac1f6b6435d0,1 28  
...

```

### Macro-F1宏平均说明（补充）

F1分数是统计学中用来衡量二分类模型精确度的一种指标。它同时兼顾了分类模型的精确率和召回率。F1分数可以看作是模型精确率和召回率的一种加权平均，它的最大值是1，最小值是0。

![equation](http://latex.codecogs.com/gif.latex?F_1%3D%5Cdfrac%7B2%7D%7B%5Cdfrac%7B1%7D%7Brecall%7D%20&plus;%20%5Cdfrac%7B1%7D%7Bprecision%7D%7D%3D2%5Cdfrac%7Brecall%5Ctimes%20precision%7D%7Brecall%20&plus;%20precision%7D)

其中

![equation](http://latex.codecogs.com/gif.latex?precision%3D%5Cdfrac%7Btrue%7E%20positive%7D%7Btrue%7E%20positive%20&plus;%20false%7E%20positive%7D)
，
![equation](http://latex.codecogs.com/gif.latex?recall%3D%5Cdfrac%7Btrue%7E%20positive%7D%7Btrue%7E%20positive%20&plus;%20false%7E%20negative%7D)

即

![equation](http://latex.codecogs.com/gif.latex?F_1%3D%5Cdfrac%7B2%5Ctimes%20TP%7D%7B2%5Ctimes%20TP%20&plus;%20FP%20&plus;%20FN%7D)

在一个多标签分类任务中，Macro-F1宏平均是指计算出每一个类的Precison和Recall后计算F1，最后将F1平均。

![equation](http://latex.codecogs.com/gif.latex?Macro%7EF_1%3D%5Cdfrac%7B1%7D%7BC%7D%5Csum%20%5Climits%5E%7BC%7D_%7Bi%3D1%7D%5Cfrac%7B2%5Ctimes%20TP_i%7D%7B2%5Ctimes%20TP_i%20&plus;%20FP_i%20&plus;%20FN_i%7D)

## 奖金

最高得分的参赛者将获得奖金：

* 第1名 - $14000
* 第2名 - $10000
* 第3名 - $8000
* 第4名 - $5000

特别奖：NVIDIA Quadro GV100 GPU

排名靠前的参赛队伍将获邀参加特别奖的比赛。具体细节见特别奖指导页。可参加特别奖比赛的队伍将在主要比赛结束后公布。

## 时间

* 2019年1月3日 – 报名截止日期。必须在此前接受比赛规则以参赛。
* 2019年1月3日 – 队伍合并截止日期。参赛选手必须在此前加入或合并队伍。
* 2019年1月10日 – 提交截止日期。

所有截止日期均为11:59 pm UTC（协调世界时，北京时间=UTC+8小时）
