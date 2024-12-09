---
title: CS 231n 总结 笔记
date: 2024-12-09 20:13
tags:
    - CS231n
categories: 机器学习笔记
mathjax: true
---

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']],

			displayMath: [['$$', '$$']]

            }
        });
    </script>
</head>

~~The last lecture of CS231n is about 3D Computer Vision. Most of the content is just introduction to some Deep Learning Algorithms and don't gain deep insight into it, which I cannot  appreciate. As a result, I will skip that lecture and write a blog to conclude my learning of CS231n(except Lecture 15, qwq).~~
~~Starting at 15th October, I have studied this course for almost 2 months and now I finnaly reached the end of the course.~~
以上是某人发电用英文写的，然后发现自己写不下去了。
大意就是最后一个Lec是关于3D视觉的，我不是很感兴趣并且PPT中的大部分内容都是仅做介绍所用，于是略过这一节，并且转而对CS231n整个的学习过程进行一次总结：
实际上我本来以为这门课的内容只是像笔记那样到CNN就为止了，但没想到Schedule里面还有很多额外的内容，让我整整多学了一个月，也是学到了很多东西。

## The first part: Deep Learning Basics
这一部分中主要学习的内容就是关于深度学习的基础：
在第一节课中学习了使用线性分类器对图片进行简单的归类并且引入了两种基础的损失函数：$\text{softmax \& SVM}$。

第二节课中对深度学习中参数的优化进行了详细地介绍，并且最后引入到梯度下降。

第三节课是对第二节课的延伸，用一些simple的例子讲解了在真实的网络中应该如何去应用梯度下降算法。

第四节课则对人工神经网络的一般化结构进行了概述。

## The second part: Perceiving and Understanding the Visual World
这一部分是课程的重点，也就是卷积神经网络在Computer Vision中的应用。
第五节课是主要是讲一些准备工作，包括数据预处理（Normalization），正则化($\ell_1$ norm, $\ell_2$ norm, dropout等等)，分类问题，回归问题等等。

第六节课介绍了在开始编写代码运行模型之前需要进行的一些检查工作，例如Gradient Checks, Monitor the Training Process, Parameter Update Methods等等。

第七节课正式进入了CNN的介绍，详细地讲解了CNN结构的各个部分，卷积层（卷积核(Filters)，感受野(Receptive Field)，膨胀卷积(Dilation Conv)，imc2ol），池化层（平均池化，最大池化），归一化层（BatchNorm, LayerNorm,......），以及一些实现的细节。

第八节课则是对归一化的处理进行了详细的介绍并且选取了几个实用的卷积模型作为例子进行解析，其中还借由ResNet介绍了一种十分常用的trick即残差连接。

第九节课介绍的内容则是相当难懂的循环网络RNN，PPT中介绍的过于简略以至于我开了两个番外篇来更详细地了解这一部分知识（Embedding Layer, BPTT, TBPTT, LSTM,......）

第十节课则是喜闻乐见的Attetion is all you need，对Transformer进行了细致地讲解。从最简单的最直观的注意力机制出发，一步步泛化深入到General Atteion Layer, Self Attention Layer, Masked Self-Attention Layer再到集大成者MultiHead Self-Attention Layer，达到了原论文的境界（？

第十一节课则是介绍了Computer Vision领域的四个主要任务Classification, Semantic Segmentation, Object Detection以及Object Segmentation。并且针对这四个任务，从之前学习过的模型出发，介绍了新的架构用以专门应对这些问题（Unpooling, Tranpose Convolution, Faster R-CNN, YOLO, Mask R-CNN）。

第十二节课是视频理解专题，从最朴素最直观的方法Early/Late Fusion出发，介绍了3D-CNN的架构，并且引入了许多优化的网络如Two-Stream Network, RCN, Spatio-Temporal Self-Attention, ViViT等等。

第十三节课可以说是对前面的总结，它介绍了对前面的模型，如何进行一些可视化操作，更好地帮助我们理解模型内部到底发生了什么，比如通过权重可视化，通过反向传播可视化等等。并且这节课还介绍了一些好玩的内容例如如何欺骗模型，如何训练模型改变图片的风格等等。

## The third Part: Generative and Interactive Visual Intelligence
这部分课程的内容就偏向于介绍性，理论推导的内容相较于前面的部分减少。

第十四节课的重点是自监督学习（All kinds of pre-text tasks, Contrastive Representation Learning）。

第十五节课介绍了生成式模型（Pixel CNN/RNN, VAEs, GANs）

第十六节课则是对强化学习做了一个广泛的介绍，梦回CS188（MDP, Value Iteration, Deep Q Learning, Policy Gradients）