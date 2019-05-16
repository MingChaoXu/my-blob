---
title: CVPR2019 PaperReading(1)
date: 2019-05-02 14:37:57
categories: 
- PaperReading
tags: 
- transfer learning
mathjax: true
---

- [ ] **On the Structural Sensitivity of Deep Convolutional Networks to the Directions of Fourier Basis Functions**
- [ ] **Striking the Right Balance with Uncertainty**
- [x] **NM-Net: Mining Reliable Neighbors for Robust Feature Correspondences**
- [x] **C2AE: Class Conditioned Auto-Encoder for Open-set Recognition**
- [ ] **Doodle to Search: Practical Zero-Shot Sketch-based Image Retrieval**
- [x] **Zero-Shot Task Transfer**
- [ ] **C-MIL: Continuation Multiple Instance Learning for Weakly Supervised Object Detection**
- [ ] **Transferrable Prototypical Networks for Unsupervised Domain Adaptation**

<!-- more -->

<!-- ### On the Structural Sensitivity of Deep Convolutional Networks to the Directions of Fourier Basis Functions
>  -->

### [Zero-Shot Task Transfer](http://arxiv.org/abs/1903.01092)

> 这篇文章是针对zero shot的任务提出了一个新的meta learning的算法——TTNet。
> 这个meta-learner 学习模型参数时从有ground truth的已知任务来迁移到新的zero-shot任务中来。
> 本篇paper是做的taskonomy的zero-shot任务，以下4个任务作为zero-shot:
> - surface-normal 
> - room layout
> - depth
> - camera pose estimation

#### Method
定义已知ground truth的m个task为$\{\tau_{1},...,\tau_{m}\}$, zero-shot task为$\{\tau_{m+1},...,\tau_{K}\}$.
用多任务学习的方法，将需要学习的meta-learning function $F(.)$建模为有m个branches的network，参数分别为$\{W_{1},...,W_{m}\}$，这些任务分支在开头没有联系，在后面通过一个$W_{common}$的block来coupled。
因此，$F(.)$可以分为两个部分，第一个部分是m个$W_{i}s$，第二个部分是$W_{common}$。

**疑问点：**
1. 本篇paper的TTnet是生成data networl的framework，但是不同的zero shot task的decoder不一样，这一点是如何保证可以生成的呢？
2. 这个work可以transfer到zero-shot的task上，我理解的关键之处在于两点：
   1. 任务间的相关矩阵，这个是通过DB算法计算出来的，由30个志愿者打分提供得分依赖
   2. 训练时的transfer model可以让模型学习到transfer的特性
~~但是我并没有看到TTnet利用到zero-shot任务的数据~~，这些任务的数据都是一样的，只是zero-shot没有相应的ground truth


**其他细节见paper**

-----------------

### [C2AE: Class Conditioned Auto-Encoder for Open-set Recognition](http://arxiv.org/abs/1904.01198)

> 这篇paper做的是open-set recognition，zero-shot相关的工作，中规中矩的unseen class分类。开放集识别是近两年一个特别新，且有实际研究价值的方向。作者提出了一个class conditioned auto-encoders的方法，训练过程中分为两个子任务：
> 1. closed-set classification
> 2. open-set identification(区分known还是unknown的class)
>
> encoder 用closed-set分类任务的pipeline学习第一个子任务，decoder通过条件重构class identity来学习第二个子任务。



-----------------

### [NM-Net: Mining Reliable Neighbors for Robust Feature Correspondences](http://arxiv.org/abs/1904.00320)
    




