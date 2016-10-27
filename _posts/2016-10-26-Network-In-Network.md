---
layout: post
title:  "Network in Network"
date:   2016-10-26
excerpt: "The reading note of network in network"
tag:
- Deep Learning Study
- Reading Note
comments: true
---

## Reference 
Lin M, Chen Q, Yan S. Network in network. arXiv preprint arXiv:1312.4400. 2013 Dec 16.


## Summary

The motivation of NiN is to enhance the discriminability within the receptive field. Specifically, each convolutional layer actually works in a specific receptive field. Within the same receptive field and using the same filter, can we increase the representation capability? One solution is NiN, namely applying a multilayer perceptron on the input before applying the filter. This is meant to use a universal function approximator (i.e., MLP) for feature extraction, instead of using feeding the latent input directly to convolutions.


The implementation is straightforward: replace 3x3 conv by 1x1 conv + 3x3 conv. Here, 1x1 conv is the MLP function approximator. 