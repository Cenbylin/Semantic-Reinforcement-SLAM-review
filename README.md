---
typora-copy-images-to: ./imgs
---

# Semantic & Reinforcement SLAM 领域调研
## Semantic SLAM
### 简介
​	至今为止，主流的SLAM方案[[1]](http://webdiis.unizar.es/~raulmur/orbslam/)都是基于处于特征点或者像素的层级，更具体地，他们往往只能用角点和边缘来提取路标。人类**是通过物体**在图像中的运动来推测相机的运动，而**非特定像素点**。

​	Semantic SLAM 是研究者试图利用物体信息的方案，其在Deep Learning的推动下有了较大的发展，成为了相对独立的分支，就方法（非设备）而言，其在整个SLAM领域所处位置如下图：

![image-20191125114443679](/Users/linancheng/for working/SLAM/review/imgs/image-20191125114443679.png)

​	目前而言，所谓**Semantic**是将基于神经网络的**语义分割、目标检测、实例分割等技术**用于SLAM中，多用于特征点选取、相机位姿估计，更广泛地说，端到端的图像到位姿、从分割结果建标记点云、场景识别、提特征、做回环检测等**使用了神经网络的方法**都可称为Semantic SLAM[[2]](https://zhuanlan.zhihu.com/p/58648284)。

​	语义和SLAM的结合有以下两点[[3]](https://book.douban.com/subject/27028215/)：

- 语义帮助SLAM。

  一方面，语义分割把运动过程中的每一张图片都带上物体标签，随后传统SLAM将带标签的像素映射到3D空间中，就能得到一个带有标签的地图。

  另一方面，语义信息亦可为回环检测、Bundle Adjustment优化带来更多的条件，提高定位精度。

  前者的工作往往称为**Semantic Mapping**，后者才认为是完整的Semantic SLAM。

- SLAM帮助语义。

  检测和分割任务都需要大量的训练数据，在SLAM中，由于我们可以估计相机的运动，那么各个物体在图像中位置的变化也可以被预测出来，**产生大量的新数据为语义任务提供更多优化条件**，且节省人工标定的成本。

### 发展




## Reinforcement SLAM