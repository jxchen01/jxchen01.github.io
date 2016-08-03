---
layout: post
title:  "Visualization of CNN models"
date:   2016-08-03
excerpt: "Hands-on practice in visualizaing and understanding CNN models and list of good sources"
comments: true
---


# Visualization of CNN Models

In general, one may want to visualize a well trained CNN model for two reasons:

* To understand the stories inside the black box
* To detect "ghost" filters which actually make little contribution for the problem or, in other words, carry little information through the CNN hierarchy. (If so, the training scheme or learning rate should be adjusted)

### Introduction

This [resource page](http://cs231n.github.io/understanding-cnn/) discusses several approaches to visualize and understand CNN models and contains a list of useful resources. 

### Code for practice

In this post, I will walk through the method described in this [paper](http://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Mahendran_Understanding_Deep_Image_2015_CVPR_paper.pdf). The code for the paper can be found [here](https://github.com/aravindhm/deep-goggle).

The basic idea of this paper is as follows. Given the feature maps at a certain layer in a CNN model, can we reconstruct the original image only based on this highly abstracted features? If not, how much can we retrieve from these feature maps?

The method used in this paper is that starting from a random input image and the reference feature maps (computed by a forward propagation through a well trained CNN) and iteratively adjust the input image so that the resulting feature maps at the corresponding layer are as close as possible to the reference feature maps. 

But, a limitation of the current code is that only simple streamline archtecture is supported, not for CNN of DAG archtectures (such as FCN). 

