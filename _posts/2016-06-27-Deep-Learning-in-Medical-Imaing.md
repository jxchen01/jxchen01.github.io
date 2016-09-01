---
layout: post
title:  "Deep Learning in Medical Imaing"
date:   2016-06-27
excerpt: "One of my current projects is to study deep learning models, such as CNN, RNN, or Reinforcement Learning, to solve medical imaging problems. "
project: true
comments: true
---

# Deep Learning in Medical Imaing

In the recent five years, deep learning has become a game changer in lots of engineering fields. Medical imaging is fountunately (or "unfortunately") one of these fields. Deep learning has become the dominating tool in numerouse applications, such as object detection (see this recent survey-like [paper](http://arxiv.org/pdf/1602.03409v1.pdf)), classification (recent nature [paper](http://www.nature.com/articles/srep21471)), diagonsis (e.g. [breast cancer](https://news.samsung.com/global/samsung-applies-deep-learning-technology-to-diagnostic-ultrasound-imaging)), and much more.

### My Deep Learning Study Note

My study note can be found [here]({{site.url}}/Think-About-Deep-Learning), including CNN, RNN, Reinforcement Learning, and lists of interesting papers to read. 

### My First Project

I developed a deep learning model for 3D segmentation in biomedical images. The paper will appear in NIPS 2016. [(NIPS 2016 Accepted Papers)](https://nips.cc/Conferences/2016/AcceptedPapers) 

The motivation of this work is that 3D medical images are not always isotropic (i.e., each voxel usually has larger scale in z-dimention than x,y-dimension.) In other words, 3D medical images are often viewed as a stack of 2D slices. So, the key idea of our solution is to perform 2D FCN in each 2D slice to abstract intra-slice context and perform LSTM in consecutive slices to extract inter-slice context. The new model opens the door to migrating 2D deep neural networks to solve 3D problems efficiently. More details are coming soon. 




