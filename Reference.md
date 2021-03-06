# 可以借鉴的网络
由于MASK R-CNN是由Faster R-CNN发展过来的，所以很多Faster R-CNN的改进思路也可以类比到MASK R-CNN上面。再通过实验数据进行对比得到是否可以得到更好的数据。<br>
当然，发现MASK R-CNN相对于Faster R-CNN的改进也是巨大的，以下列出相对于Faster R-CNN的不同：<br>
1）、使用ResNet101网络<br>
2）、将Roi Pooling 层替换成了RoiAlign<br>
3）、添加并列的MasK层<br>
4）、由RPN网络转变成FPN网络<br>
## 改进思路图
![Image text](https://github.com/happyhk/Academic/blob/main/resource/two-stage.png)
### 基于特征网络的改进
（1）PVANet：<br>
参考文献：[链接](https://blog.csdn.net/qq_35608277/article/details/80440719)<br>
（2）Light-Head R-CNN：<br>
参考文献：[链接](https://blog.csdn.net/Zealoe/article/details/78606116?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param)<br>
### 基于更精准的RPN
（1）、MR-CNN(2015)：<br>
往的目标检测模型在提取完 region proposals 后，直接将生成的 region 输入网络。那么实际上，在输入网络之前，我们也可以对 region 再进行变换。本篇论文就是这种思想。如果在 region 输入网络之前，对 region 进行变换。例如，我们只看一部分 region，或者我们将 bounding box 放大，关注其上下文环境。对于最终的分类和 bounding box 的回归应该是都会有所提高的。<br>
  本篇论文的主要贡献：<br>
  提供了一些丰富的对象表示，能够捕获各种不同的判别外观的因素。<br>
  使用语义分割的弱监督方式来感知目标检测中的对象。<br>
  使用Iterative Localization 和 Bounding box voting 提高了目标定位的能力。<br>
参考文献：[链接](https://blog.csdn.net/m0_45962052/article/details/104901825)<br>

（2）、FPN（2017）:<br>
以往多数的object detection算法都是只采用顶层特征做预测，但我们知道低层的特征语义信息比较少，但是目标位置准确；高层的特征语义信息比较丰富，但是目标位置比较粗略。另外虽然也有些算法采用多尺度特征融合的方式，但是一般是采用融合后的特征做预测，而本文不一样的地方在于预测是在不同特征层独立进行的。这篇文章，作者利用了深度卷积神经网络固有的多尺度、多层级的金字塔结构去构建特征金字塔网络，使用一种自上而下的侧边连接，在所有尺度构建了高级语义特征图，这种结构就叫特征金字塔网络（FPN）。其在特征提取上改进明显，把FPN用在Faster R-CNN上，在COCO数据集上，一举超过了目前所有的单模型（single-model）检测方法。<br>
参考文献：[链接](https://blog.csdn.net/xyj1536214199/article/details/80895716?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param)
（3）、CRAFT（2016）：<br>
参考文献：[链接](https://blog.csdn.net/App_12062011/article/details/77944957)<br>
### 更完善的ROI分类
（1）、R-FCN(2016)<br>
R-FCN是在Faster R-CNN的框架上进行改造，第一，把base的VGG16换车了ResNet，第二，把Fast R-CNN换成了先用卷积做prediction，再进行ROI pooling。由于ROI pooling会丢失位置信息，故在pooling前加入位置信息，即指定不同score map是负责检测目标的不同位置。pooling后把不同位置得到的score map进行组合就能复现原来的位置信息。<br>
参考文献：[链接](https://www.cnblogs.com/lillylin/p/6277094.html)<br>
（2）、Cascade R-CNN(2018)<br>
该算法对于任意的R-CNN（Faster rcnn、FPN、R-FCN等）都可以带来2到3个点的AP提升！！！ 而且实现十分简单，已经使用Pytorch在Pascal VOC上复现论文。<br>
参考文件：[链接](https://zhuanlan.zhihu.com/p/42553957)<br>
### 基于样本后处理的改进
（1）、OHEM（2016）：<br>
OHEM是挖掘利用现有的困难样本，具有现实意义。<br>
参考文献：[链接](https://zhuanlan.zhihu.com/p/59002127)<br>
（2）、soft NMS（2017）：<br>
参考文献：[链接](https://blog.csdn.net/u014380165/article/details/79502197)<br>
（3）、A-Fast-RCNN(2017)：<br>
这篇论文我还是很感兴趣的，毕竟用到了生成对抗的思想，回头再仔细研究一下。哈哈~<br>
参考文献：[链接](https://blog.csdn.net/Jesse_Mx/article/details/72955981)
### 基于加大minibatch的改进
（1）、MegDet(2018)：<br>
通过加大minibatch来提升网络性能。<br>
参考文献：[链接](https://zhuanlan.zhihu.com/p/55775948)
