---
layout: post
title:  "Deep Active Contour"
date:   2016-09-24
excerpt: "Reading Note of Deep Active Contour"
tag:
- Deep Learning Study
- Reading Note
comments: true
---

## Reference

Rupprecht C, Huaroc E, Baust M, Navab N. Deep Active Contours. arXiv preprint arXiv:1607.05074. 2016. [(link)](https://arxiv.org/abs/1607.05074)

## Summary

The core idea of this paper is very nice: using deep learning model to guide the movement of active contours. In specific, a patch is selected at each point along the contour. A CNN model is applied on this patch to predict the flow vector. Then, the contour is updated (i.e. moving) according to the flow vectors. Also, certain regulation is applied to garantee the stability. 

To integrate a CNN model with classic methods and apply CNN in an "on-the-go" manner, a key issue is how to formulate the model (e.g., input/output) and how to train (e.g., availability and validity of training data). This paper gives a nice solution. 

* Model: For each point along the contour, the extracted patch is aligned with the normal direction. In this sense, the model is well formulated: Given the context "ahead", the model learns how to move.  
* Training: To make the training data covers the situations may encounter on-the-go as much as possible, the signed distance map (SDM) is calculated from the ground truth. Then, sampling the points along different level lines in SDM is a good means to simulate the points along the evolving contours.

## Issues

(1) Some general issues of active contore cannot be avoid even with the help from an effective CNN model. For instance, regulation must be carefully chosen. As demonstrated in Fig.4 of the paper, some parts of the object with high curvature may not be extracted due to a strong regulation. 

(2) It seems like the method requires the initial contour is close to the object. In other words, we roughly know where the object is. Then, what if we simply apply some kind of FCN? 
