---
layout: post
title:  "Deep Learning in Medical Imaging"
date:   2016-06-27
excerpt: "One of my current projects is to study deep learning models, such as CNN, RNN, or Reinforcement Learning, to solve medical imaging problems. "
project: true
comments: true
---

# Deep Learning in Medical Imaging

In the recent five years, deep learning has become a game changer in lots of engineering fields. Medical imaging is fountunately (or "unfortunately") one of these fields. Deep learning has become the dominating tool in numerouse applications, such as object detection (see this recent survey-like [paper](http://arxiv.org/pdf/1602.03409v1.pdf)), classification (recent nature [paper](http://www.nature.com/articles/srep21471)), diagonsis (e.g. [breast cancer](https://news.samsung.com/global/samsung-applies-deep-learning-technology-to-diagnostic-ultrasound-imaging)), and much more.

Recent survey papers on "Deep Learning in Medical Image Analysis": [paper_1](http://www.annualreviews.org/doi/abs/10.1146/annurev-bioeng-071516-044442),[paper_2](https://arxiv.org/abs/1702.05747)

### My Deep Learning Study Note

My study note can be found [here]({{site.url}}/Think-About-Deep-Learning), including CNN, RNN, Reinforcement Learning, and lists of interesting papers to read. 

### My Project 1: Deep Learning For 3D BioMedical Image Segmentation

I developed a deep learning model for 3D segmentation in biomedical images. The paper is published in NIPS 2016. [(NIPS version)](http://papers.nips.cc/paper/6448-combining-fully-convolutional-and-recurrent-neural-networks-for-3d-biomedical-image-segmentation) [(ArXiv version)](https://arxiv.org/abs/1609.01006).

The motivation of this work is that 3D medical images are not always isotropic (i.e., each voxel usually has larger scale in z-dimention than x,y-dimension.) In other words, 3D medical images are often viewed as a stack of 2D slices. So, the key idea of our solution is to perform 2D FCN in each 2D slice to abstract intra-slice context and perform LSTM in consecutive slices to extract inter-slice context. The new model opens the door to migrating 2D deep neural networks to solve 3D problems efficiently. 

A list of other related methods for 3D segmentation:

* V-Net: [Link](https://arxiv.org/abs/1606.04797)
* 3D U-Net: [Link](https://arxiv.org/abs/1606.06650)
* VoxResNet: [Link](https://arxiv.org/abs/1608.05895)

### My Project 2: Deep Learning For 2D BioMedical Image Segmentation

Deep learning has been widely used for 2D image segmentation, espeically after the development of fully convolutional network. I developed a deep learning model 2D biomedical image segmentation, which employs multi-scale feature reusing to improve the model's representation capability and reduce the model's redundancy. The paper is accepted to MICCAI 2017. [(ArXiv version)](https://arxiv.org/abs/1705.11053)

A list of other related methods for 2D segmentation:

* U-Net: [Link](https://arxiv.org/abs/1505.04597)
* DCAN: [Link](http://www.cv-foundation.org/openaccess/content_cvpr_2016/html/Chen_DCAN_Deep_Contour-Aware_CVPR_2016_paper.html)





