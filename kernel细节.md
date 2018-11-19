这里是kernel上的一些琐碎的细节，感觉有一定参考价值的都往这写吧，不用在意排版什么的

### pretrained ResNet34 with RGBY (0.460 public LB)

效果：validation F1 score of the model is ~0.65-0.7，0.460 public LB score in V11 of the kernel

数据增强: aug_tfms = [RandomRotate(30, tfm_y=TfmType.NO), RandomDihedral(tfm_y=TfmType.NO), RandomLighting(0.05, 0.05, tfm_y=TfmType.NO)]

训练集mean and std: stats = A([0.08069, 0.05258, 0.05487, 0.08282], [0.13704, 0.10145, 0.15313, 0.13814])

损失函数：为了解决各个类别样本数量的不平衡，采用了focal loss（作者说有用但感觉没啥道理，需要做实验证实）；<br>sigmoid要放在loss里计算（写loss函数要注意)

网络初始化4个channel：Y channel 置零，评论里说用别的通道初始化（可以试试）。网络不同部分设置不同学习率（也要试）。

27类手调阈值[0.54841 0.59038 0.58134 0.55174 0.58924 0.61733 0.50403 0.57952 0.50263 0.44694 0.37854 0.60698 0.58683 0.57907 0.5511 0.50602 0.48044 0.48919 0.51825 0.5246 0.40525 0.50145 0.51568 0.57143 0.68486 0.51439 0.49912 0.50548]<br>
（emmm加了focal loss之后阈值在0.5附近）<br>
F1 macro: 0.7203957181622302 F1 macro (th = 0.5): 0.684800026809271 F1 micro: 0.7634674310566374<br>
测试集27类比例 (true): [0.40508 0.03764 0.11454 0.04633 0.05759 0.07593 0.03475 0.08848 0.00097 0.00097 0.00097 0.03475 0.02477 0.01705 0.03121 0.00032 0.01544 0.00547 0.03089 0.04311 0.0074 0.12806 0.02703 0.09717 0.00933 0.27156 0.01351 0.00064]

### Protein Atlas - Exploration and Baseline

做了一些相关分析，比如endosomes lysosomes一定同时出现（这个是fc层可以学出来的，关键是图像层面上有什么可以利用的信息）

### Exploring the human protein atlas images

用seeded watershed segmentation（种子分水岭分割），从细胞核（blue channel）开始分割，传统算法开启闭合。阈值不太好取？

