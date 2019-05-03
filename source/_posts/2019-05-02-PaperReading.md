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
- [ ] **NM-Net: Mining Reliable Neighbors for Robust Feature Correspondences**
- [ ] **Efficient Video Classification Using Fewer Frames**
- [ ] **Doodle to Search: Practical Zero-Shot Sketch-based Image Retrieval**
- [ ] **Zero-Shot Task Transfer**
- [ ] **C-MIL: Continuation Multiple Instance Learning for Weakly Supervised Object Detection**
- [ ] **Transferrable Prototypical Networks for Unsupervised Domain Adaptation**


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


    



