
<!-- ---
layout: post
title:  "Think about Deep Learning"
date:   2016-06-27
excerpt: "This is post excerpt. You can delete this line if you want an auto generated excerpt."
project: true
comments: true
---
-->


# Think about Deep Learning 

I built this webpage to host my notes, thoughts and resources I collected during my study of deep learning (DL). Some of the tutorials were written by myself, while a large number of online rescoures are also included. Since my researches focus on medical image analysis, my DL study was aiming more at medical imaging applications. 

## Introduction to Convolutional Neural Network (CNN)

See my post [here](https://docs.google.com/a/nd.edu/presentation/d/1TMbLXgk1oF8YUJYkX1zXPAmr7L4e24XIuk8Gz370ShM/present?usp=sharing) 

## Introduction to Recurrent Neural Network (RNN)

See my post [here](http://www3.nd.edu/~jchen16/2016-04-26-introduction-to-rnn.html)

## Introduction to Deep Reinforcement Learning 

I don't have too much experience in deep reinforcement learning (DRL). To my understanding, this is a more general deep learning algorithm, but relatively less tailored for specific computer vision problems. 

Here is an awesome introduction to DRL: [link](https://www.nervanasys.com/demystifying-deep-reinforcement-learning/). Several additional sources can be found in the external links in this post.

DRL is attracting more and more attentions nowadays. It is probably due to the success of DeepMind (AlphaGo). One key algorithm is the so-called Deep Q-Learning. Some implementations can be found at [link1](https://github.com/tambetm/DeepMind-Atari-Deep-Q-Learner), [link2](https://github.com/SeanNaren/TorchQLearningExample), [link3](https://github.com/kuz/DeepMind-Atari-Deep-Q-Learner), and [link4](https://github.com/iassael/torch-bootstrapped-dqn).

A very interesting work published recently is to use Deep Q-learning to accelerate the training of CNN ([paper](http://arxiv.org/abs/1606.01467)).

More resources: 
* A post from Andrej Karpathy, [link](http://karpathy.github.io/2016/05/31/rl/)
* The most recent tutorial [(link)](http://icml.cc/2016/tutorials/deep_rl_tutorial.pdf) on ICML 2016.

## Papers to read

* Unsupervised Learning: This is the most urgent thing I want to learn. 
	* A general overview: [link](https://culurciello.github.io//tech/2016/06/10/unsup.html)
	* ~~Insight from Yann LeCunn and the Facebook AI group about adversial network, a new paradigm for unsuperised learning. [link](https://code.facebook.com/posts/1587249151575490/a-path-to-unsupervised-learning-through-adversarial-networks/)~~ and a key paper introducing [DCGAN](http://arxiv.org/abs/1511.06434).  
	* A tutorial on Variational Autoencoder, [paper](http://arxiv.org/abs/1606.05908)
	* A comprehensive tutorial on the concept of "adversarial network", a very promising solution to unsupervised learning. [link](https://ishmaelbelghazi.github.io/ALI/)
* Instance Segmentation using deep learning: performing segmentation on the instance level (maybe one by one in a recurrent framework or in one shot)
	* using recurrent attention, [link](http://arxiv.org/abs/1605.09410)
	* also predict depth, [link](http://arxiv.org/abs/1604.05096)
	* a recent survey, [link](http://arxiv.org/abs/1602.06541)
	* instance sensitive FCN by Kaiming He, [link1](http://arxiv.org/abs/1603.08678) and [link2](http://arxiv.org/abs/1512.04412)
	* Combinining with CRF [link1](https://arxiv.org/abs/1412.7062) and [link2](http://arxiv.org/abs/1511.03328)
	* ENet: for real-time application [link](https://arxiv.org/abs/1606.02147)
	* Dealing with high resolution images, [paper](http://arxiv.org/abs/1606.02585v1)
* Image colorization and syhthesis using deep learning:
	* MFR+CNN, [link](http://arxiv.org/pdf/1601.04589v1.pdf)
	* a webpage describing recent works, [link](http://richzhang.github.io/colorization/)
	* deep colorization [link](http://www.cs.cityu.edu.hk/~qiyang/publications/iccv-15.pdf)
	* a recent work [link](http://arxiv.org/pdf/1603.08511.pdf)
* Expressive power of DNN: People may say DNN is able to express very complex non-linear function. But how to quantify such capability? I just found this paper to read. [link](http://arxiv.org/abs/1606.05336) 
* New Schemes for parameter initialization in CNN, two papers in ICLR 2016: [paper1](http://arxiv.org/pdf/1511.06856v2.pdf) [paper2](http://arxiv.org/pdf/1511.06422v7.pdf)
* Weight Normalization: a new scheme for better training of CNN. [link](https://arxiv.org/pdf/1602.07868.pdf)
* SqueezeNet: A CNN using much less memory without reducing accuracy. [paper](http://arxiv.org/abs/1602.07360)
* Style transfer [paper](http://arxiv.org/abs/1508.06576) and [code](https://github.com/fzliu/style-transfer)
* Extreme Learning machine, another type of machine learning algorithms which is closers to human brain [review paper](http://www.sciencedirect.com/science/article/pii/S0893608014002214)
* Binary CNN: [paper1](http://arxiv.org/abs/1511.00363) and [paper2](http://arxiv.org/abs/1603.05279)
* CNN on graphs: Extend classic CNN which applies on grids (e.g., images) to graph data [paper1](http://arxiv.org/abs/1605.05273) and [paper2](http://arxiv.org/abs/1506.05163)
* A comprehensive comparison of different choices in each component in CNN, such as different activation function or different pooling. [link](http://arxiv.org/abs/1606.02228)
* CNN in convert sketch to image, [link](https://arxiv.org/abs/1606.03073)
* Piecewise Training [link](http://arxiv.org/abs/1504.01013)
* Object detection using R-FCN, [link](https://arxiv.org/abs/1605.06409)
* Pixel Recuurent Neural Network (best paper in ICML 2016), [link](http://arxiv.org/abs/1601.06759?url_type=39&object_type=webpage&pos=1)
* Edge detection by DNN. [github link](https://github.com/s9xie/hed/blob/master/README.md)
* A nice guide of Tensorflow, [link](https://www.oreilly.com/learning/hello-tensorflow) 





