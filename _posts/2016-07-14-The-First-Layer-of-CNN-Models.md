---
layout: post
title:  "The First Layer of CNN models"
date:   2016-07-14
tags: [Deep Learning Study]
excerpt: "About the special role that the initial layers in a CNN model is playing"
comments: true
---

# The First Layer of CNN models

I have never thought about the initial layer carefully untill reading this [blog](http://linkis.com/github.io/kDnqR). THe initial layer is rather important as it casts the input features of each element (e.g. RGB value at each pixel) into a feature space with much higher dimensionality. Analogous to feature engineering in machine learning, this step casts the problem from one space to another, while the data in the new space are (non-)linear combination of the data in the old space. 

Thus, two factors stand out.
+ The complexity of the mapping function
+ The domain of the mapping function

The complexity means how many convolutional layers (despite of kernel sizes) are employed before downsampling. The domain is also important, by which I mean the kernel sizes actually. For example, ResNet uses a 7-by-7 convolution to process the input.

