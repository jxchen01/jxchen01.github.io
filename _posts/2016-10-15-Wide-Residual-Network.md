---
layout: post
title:  "Wide Residual Network"
date:   2016-10-15
excerpt: "Reading Note of Wide Residual Network"
tag:
- Deep Learning Study
- Reading Note
comments: true
---

## Reference

Zagoruyko S, Komodakis N. Wide Residual Networks. arXiv preprint arXiv:1605.07146. 2016 May 23. [(link)](https://arxiv.org/abs/1605.07146)

## Summary

Residual network (ResNet) has been shown to be a very successful breakthrough of CNN in the recent two years. The key idea of ResNet is two-folds: replacing convolutions in classic CNN by residual blocks, and increasing the depth of CNN after adopting the residual blocks. Then, the improved performance of ResNet may be due to either the effectiveness of the residual blocks or due to the extremely deep layers. This paper argues that the former one is the main reason. 


Important messages from the paper:

* The main power of deep residual networks is in residual blocks, and the effect of depth is supplementary.
* Widening the convolutional layers by adding more feature planes is the most effective way to increase representational power of residual blocks.
* Dropout should be inserted between convolutional layers.

In this paper, the authors use thorough experiments to demonstrate the above claims, where new state-of-the-art on several benchmarks have been achieved.