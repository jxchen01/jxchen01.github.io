---
layout: post
title:  "Introduction to MatConvNet"
date:   2016-07-05
excerpt: "A brief introduction to MatConvNet, a deep learning framework in Matlab. Installation, basic usage, coding philosophy, and examples will be introducted."
comments: true
---

# Introduction to MatConvNet



## Installation

I have successfully installed it on Windows 7. It is not hard if you follow the guide [here](http://www.vlfeat.org/matconvnet/install/). But, setting up all the required compiler on Windows 7 made me crazy. I would suggest to use Visual Studio (Community Edition) as the compiler and install the required .Net library (not the newest one). 

One terrible issue I encounted was that cl.exe (a .net library) cannot be found anyway. One possible solution was suggested [here](http://stackoverflow.com/questions/32091593/cannot-install-windows-sdk-7-1-on-windows-10).

## Introduction

In general, MatConvNet supports two types of model: simple chain model and DAG (directed acyclic graph) model. It is very easy to implement any CNN model as long as the layers are supported (even multiple criterions). (For instance, dilated convolution is not supported, yet. So, it may take considerable time to write your own.)

There are several nice things about MatConvNet. 
* It is easy to understand and tweak, if you are already familiar with Matlab. 
* It is easy to set different learning rate for each layer, which is necessary for fine tuning
* It is easy to assign different weights on the ground truth images. This is important when errors in certain areas should be highly penalized. 

The key limitation of MatConvNet is the limited number of supported functions, such as different types of layers, different optimization algorithms, etc.. 


## Ready-to-Use Examples

An illustration of VGG using MatConvNet. See [link](http://www.robots.ox.ac.uk/~vgg/practicals/cnn/)

A nice github repository containing quite a few CNN structures can be found [here](https://github.com/jxchen01/matconvnet-calvin). 

A Matlab plugin has been developed to visualize layers in MatConvNet models. See [link](http://vision03.csail.mit.edu/cnn_art/index.html)

## Build from Scratch

Basically, building a new CNN model contains three parts: declaring the neural network architecture, preparing training data, and setting the optimizer for training. The main function looks like:

	function my_deep_learning_exp(varargin)
		run matconvnet/matlab/vl_setupnn ;
		addpath matconvnet/examples ;
		
		rng(3); %%% for reproducibility
		
		options_for_training = struct( ... ... );  %%% setting the training parameters
		
		%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
		%%%%%%% define and initialize the CNN model %%%%%%%%
		%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
		my_deep_learning_model = modelInitialization( *some parameters*);
		my_deep_learning_model.initParams() ;
		
		%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
		%%%%%%%%%%%% prepare dataset information %%%%%%%%%%%
		%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
		im_database.images.id=1:1:num_of_images;
		set_index = randperm(num_of_images);
		% split training, validation, and evaluation datasets
		im_database.images.set=ones(1,num_of_images);
		im_database.images.set(set_index(floor(0.7*num_of_image):1:floor(0.9*num_of_image))=2; % validation set
		im_database.images.set(set_index(floor(0.9*num_of_image)+1:1:end)=3; % validation set
		
		% assign other necessary paramters
		im_databased.size = [Sw, Sh, Sd];
		
		%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
		%%%%%%%%%%% perform training iteratively %%%%%%%%%%%
		%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
		[net, info] = cnn_train_dag(my_deep_learning_model, im_database, getBatch_fcn(options_for_training), options_for_training);


### Define the CNN Model Architecture

Most of the models I used for researches have a DAG structure, which usually more flexible than a simply chained model. Therefore, I will use DAG model as examples in this part.

Usually, it is a good practice to write the network architecture definition in a separated function, like the following:
	function net = modelInitialization(parameters)
		net=dagnn.DagNN();
		net.addLayer(...);
		net.addLayer(...);
		...
The key idea of building a DAG model in MatConvNet is to declare "This layer connectes whom to whom". For instance, 

	Layer1 = dagnn.XXXX(...) ;
	net.addLayer('layer_1', Layer1, {'v1','v2'}, {'v3'}, {'param_1', 'param_2'});

declares a layer of type XXXX (see [all supported layers](https://github.com/vlfeat/matconvnet/tree/master/matlab/%2Bdagnn)), which connects v1 and v2 to v3. The layer contains two sets of variables 'param_1' and 'param_2' (e.g., the kernel and bias terms in a convolution layer). Here, v3 is the output of this layer; v1 and v2 can be the output of any layer processed before "Layer1" or the input. 

It is worth mentioning that the Loss function used in images can be found [here](https://github.com/vlfeat/matconvnet-fcn/blob/master/SegmentationLoss.m), which normalizes the loss over the entire image by assiging a proper weight. 
		

### Prepare the Training Data

		function fn = getBatch_fcn(opt)
		%%%%% defining the r
fn = @(im_datebase,batch) my_deep_learning_getBatch(im_datebase,batch,options_for_training.trainingdata) ;

### Setting Optimizer for Training