---
layout: post
title:  "Densely Connected CNN"
date:   2016-10-24
excerpt: "Reading Note of Densely Connected Convolutional Network"
tag:
- Deep Learning Study
- Reading Note
comments: true
---

## Reference

Huang G, Liu Z, Weinberger KQ. Densely Connected Convolutional Networks. arXiv preprint arXiv:1608.06993. 2016 Aug 25. [(link)](https://arxiv.org/abs/1608.06993)

## Summary


The main contribution of this paper is to introduce an architecture with dense shortcut connection, and experimentally demonstrate several insightful observations about shortcut connection. 

The method is inspired from the recent works that a CNN can be made much deeper after adding shortcut connections (otherwise, a very deep CNN is hard to train due to vanishing gradient). So, the method goes to one extreme: each convolution layer is connected to all layers before it. 


#### Highlight
* DenseNet layers are very narrow (e.g., 12 feature maps), so the whole network actually requires fewer parameters than traditional network
* DenseNet explores feature reuse to the most, yielding a highly condensed model
* Dropout is not needed in DenseNet, which is already less prone to overfitting by itself.
* DenseNet achieves deep supervision (i.e., auxiliary criterion attached to hidden layers to enforce discriminative feature learning in hidden layers) in the form of shortcut connection to the final layer.


#### Key observations about shortcut:
* Shortcut connections have a regularizing effects on the network, which tends to avoid overfitting
* Long distance dependency through shortcut connection may be necessary to increase the network capability.
* Shortcut can help to achieve deep supervision.


#### Implementation details:
* Dense Block: When the feature maps are of different scale (i.e., after different numbers of pooling), the shortcut may be troublesome. So, DenseNet only uses dense connection within each Dense Block, in which there is no pooling layer. Dense Blocks are connected sequentially via transition layers, which consist of pooling and 1x1 convolutions.
* BN+ReLU+Conv becomes a standard composition, according to Kaiming’s paper.
* Growth Rate: Because each layer has input from all preceding layers within the same Dense Block, the number of feature maps grows fast. The growth rate is the hyperparameter to consider.
Torch code is available.
