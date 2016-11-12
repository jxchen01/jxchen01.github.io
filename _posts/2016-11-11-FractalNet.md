---
layout: post
title:  "FractalNet"
date:   2016-11-11
excerpt: "The reading note of FractalNet"
tag:
- Deep Learning Study
- Reading Note
comments: true
---

## Reference 
Larsson G, Maire M, Shakhnarovich G. FractalNet: Ultra-Deep Neural Networks without Residuals. arXiv preprint arXiv:1605.07648. 2016 May 24. [Link](https://arxiv.org/abs/1605.07648)


## Summary

One trend in designing CNN architecture is to employ proliferative paths. FractalNet arranges the paths in a fractal pattern. 

A fractal blocks is shown below.

<img src="http://people.cs.uchicago.edu/~larsson/fractalnet/overview.png" alt="Adobe_Reader_Screen_Shot_1" style="width: 400px;"> 

The fractalNet connects a sequence of fractal blocks by inserting pooling layers between the blocks.

#### Drop Path

It is easy to observe that there lots of paths in each fractal block. So, the authors propose a generalization of dropout mechanism for fractalNet, called Drop-Path, which randomly mutes certain paths (instead of muting connection as in dropout). 

#### Insigh of fractal structure 

1. The proliferative paths implicitely union a larger amount of sub-networks of various depths. To some extent, fractalNet shares the same spirit with ResNet, namely very deep network with effectively shorter paths for gradient propagation.

2. Viewing a fractal block along a horizontal cross-section reveals that fractalNet also shares similar spirit with the Inception module in GoogleNet. 

3. Drop-path acts as a regulation of avoid co-adaptation of subpaths. As a result,  shallow subnetworks provide a quick answer, while deeper subnetworks provides a more accurate answer. The training of fractalNet actually exhibits a lateral student-teacher paradigm, where shallow subnetworks and deeper subnetworks are implicitly coupled and share guidence information bidirectionaly.  





