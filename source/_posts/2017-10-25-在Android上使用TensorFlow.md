---
title: 在Android上使用TensorFlow
date: 2017-10-25 18:38:18
categories: 技术心得
tags:
    - Android
    - TensorFlow
cover_picture: images/androidAndTensorFlow.png
---
![androidAndTensorFlow](/images/androidAndTensorFlow.png)
### 一、简介

由于最近做的一个项目，需要在手机上做机器学习来识别不同的握姿，于是准备使用[TensorFlow](https://www.tensorflow.org/)库来进行训练和识别。一个核心的问题是训练好了模型之后如何在手机上运行TF进行识别，查找了很多资料后发现相关资料比较杂乱，官方例子也不是很清楚，在经历了近一周的摸爬滚打之后终于成功跑通了整个流程，于是在这里记录下来以备查阅。

本文的主要目标是使用TensorFlow训练好模型后，如何将模型在Android上运行起来。整个过程在Windows 10系统和Android Studio上亲测可用。

本文主要参考资料: [Tutorial: Build Your First Tensorflow Android App](https://omid.al/posts/2017-02-20-Tutorial-Build-Your-First-Tensorflow-Android-App.html) ,对于其中部分不清楚（以及不能用的）部分进行了修正。

### 二、整体流程

整个项目完整的流程如下：
<div style="text-align:center">
```sequence
Participant 手机 as a
Participant PC as b
a->b: 训练数据
Note over b: 生成模型文件
b->a: 模型文件
Note over a: 运行
Note over a: 结果
```
</div>


