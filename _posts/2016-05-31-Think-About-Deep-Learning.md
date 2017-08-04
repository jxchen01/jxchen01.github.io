---
layout: post
title:  "Think about Deep Learning"
date:   2016-05-31
excerpt: "My deep learning study note and reading list."
tag:
- Deep Learning Study
comments: true
---
[last updated on Aug. 4, 2017]

# Think about Deep Learning 

I built this webpage to host my notes, thoughts and resources I collected during my study of deep learning (DL). Some of the tutorials were written by myself, while a large number of online rescoures are also included. Since my researches focus on medical image analysis, my DL study was aiming more at medical imaging applications. 

## Introduction to Convolutional Neural Network (CNN)

See my post [here](https://docs.google.com/a/nd.edu/presentation/d/1TMbLXgk1oF8YUJYkX1zXPAmr7L4e24XIuk8Gz370ShM/present?usp=sharing) 

## Introduction to Recurrent Neural Network (RNN)

See my post [here](http://www3.nd.edu/~jchen16/2016-04-26-introduction-to-rnn.html)

## Introduction to Deep Reinforcement Learning 

I don't have too much experience in deep reinforcement learning (DRL). To my understanding, this is a more general deep learning algorithm, but relatively less tailored for specific computer vision problems. 

DRL is attracting more and more attentions nowadays. It is probably due to the success of DeepMind (AlphaGo). One key algorithm is the so-called Deep Q-Learning. Some implementations can be found at [link1](https://github.com/tambetm/DeepMind-Atari-Deep-Q-Learner), [link2](https://github.com/SeanNaren/TorchQLearningExample), [link3](https://github.com/kuz/DeepMind-Atari-Deep-Q-Learner), and [link4](https://github.com/iassael/torch-bootstrapped-dqn).

Jump Start:

* Essential Idea of DRL: [(link)](https://www.nervanasys.com/demystifying-deep-reinforcement-learning/). Several additional sources can be found in the external links in this awesome post.
* High-level description of each key component in DRL: Andrej Karpathy's blog [(link)](http://karpathy.github.io/2016/05/31/rl/)
* Complete Introduction: David's course [(link)](http://www0.cs.ucl.ac.uk/staff/d.silver/web/Teaching.html) and John Schulman's course [(link)](http://rll.berkeley.edu/deeprlcourse/#syllabus) 


More resources: 

* A very interesting work published recently is to use Deep Q-learning to accelerate the training of CNN ([paper](http://arxiv.org/abs/1606.01467)).
 
* The most recent tutorial [(link)](http://icml.cc/2016/tutorials/deep_rl_tutorial.pdf) on ICML 2016. (Note: Really inspiring!)

* An example to practice [(link)](https://jaromiru.com/2016/10/03/lets-make-a-dqn-implementation/)

## Papers to read

* Must read: A paper from Arterys, a startup in the bay area. [(Link)](https://arxiv.org/abs/1704.04296) The method itself is not of great interest. But, I am eager to see how deep learning is used in startups and how they present the methods. 
* Another paper by a startup, Imagia. [(Link)](https://arxiv.org/abs/1702.05174) Co-authored by Yoshua Bengio. The method is also very interesting.  
* Dual Path Network [Link](https://arxiv.org/abs/1707.01629)
* Active learning and fine tuning for biomedical image analysis [Link](http://openaccess.thecvf.com/content_cvpr_2017/papers/Zhou_Fine-Tuning_Convolutional_Neural_CVPR_2017_paper.pdf)
* Quick Read:
	* Dynamic steerable blocks [Link](https://arxiv.org/abs/1706.00598) 
	* steerable CNN [Link](https://arxiv.org/abs/1612.08498)
	* Fine tuning for medical image analysis [Link](https://arxiv.org/abs/1706.00712)
	* segAN [Link](https://arxiv.org/abs/1706.01805)
	* Morphology error detection [Link](https://arxiv.org/abs/1705.10882)
	* dilated residual network [Link](https://arxiv.org/abs/1705.09914)
	* anatomically constrained 3D FCN [Link](https://arxiv.org/abs/1705.08302)
	* for tracking [Link](https://arxiv.org/abs/1705.06368)
	* 3D FCN and random walk [Link](https://arxiv.org/abs/1704.06544)
	* Hierarchical 3D FCN [Link](https://arxiv.org/abs/1704.06382)
	* SeGAN [Link](https://arxiv.org/abs/1703.10239)
	* DNN for multi-task multi-modality medical image segmentation [Link](https://arxiv.org/abs/1704.03379)
	* review on DNN for semantic segmentation [Link](https://arxiv.org/abs/1704.06857)
	* Proximal Segmentation in medical images [Link](https://arxiv.org/abs/1704.06176)
	* Wavelete Residual Network [Link](https://arxiv.org/abs/1707.09938)
	* Multi-modale CNN for brain tumor segmentation [Link](https://arxiv.org/pdf/1706.08124.pdf)
	* Recurrent context learning [Link](https://arxiv.org/pdf/1707.04912.pdf)
	* 3D deep supervision [Link](https://arxiv.org/abs/1607.00582), and another similar one [Link](https://arxiv.org/abs/1706.01148)
	* Predicting the ambiguity of foreground object [Link](https://arxiv.org/pdf/1705.00366.pdf)
* ~~Deformable Convolution Network [Link](https://arxiv.org/abs/1703.06211)~~
* Guide to semantic segmentation with deep learning, by Qure.ai [Link](http://blog.qure.ai/notes/semantic-segmentation-deep-learning-review)
* Xception, depthwise separable convolutions. [Link](https://arxiv.org/abs/1610.02357)
* CortexNet [Link](https://arxiv.org/abs/1706.02735)
* Rethinking Atrous Convolution [Link](https://arxiv.org/abs/1706.05587)
* Train longer, generalize better [Link](https://arxiv.org/abs/1705.08741),[Github](https://github.com/eladhoffer/bigBatch)
* Evaluation without ground truth:
	* no-gold-standard evaluation, [Link](http://medicalimaging.spiedigitallibrary.org/mobile/article.aspx?articleid=2608878)
	* pull the plug: a framework for coordinating computer segmentation and human annotation. [Link](http://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gurari_Pull_the_Plug_CVPR_2016_paper.pdf)
	* Evaluating segmentation errors without ground truth [Link](https://pdfs.semanticscholar.org/f470/d0a22585a221aec09c668b7fbd061fc9dc20.pdf) 
* Train ImageNet in 1 Hour [Link](https://research.fb.com/publications/ImageNet1kIn1h/)
* Apple's ML journal: [Link](https://machinelearning.apple.com/2017/07/07/GAN.html)
* The future of deep learning, by the Francois Chollet. [Link](https://blog.keras.io/the-future-of-deep-learning.html)
* Pixel deconvolution network [Link](https://arxiv.org/abs/1705.06820)
* ~~Dense Transformer Network [Link](https://arxiv.org/abs/1705.08881)~~
* An intereting application of adversarial network in segmentation [Link](https://arxiv.org/abs/1704.05712)
* Network Dissection [Link](http://netdissect.csail.mit.edu/final-network-dissection.pdf)
* Interpretable explanation of black box by meaningful pertubation [Link](https://arxiv.org/abs/1704.03296),[Github](https://github.com/jacobgil/pytorch-explain-black-box)
* Incorporating Built-in Prior to deep learning for segmentation: [Link](https://arxiv.org/abs/1706.02189)
* Registration: 
	* Deep Face Alignment: [Link](https://arxiv.org/abs/1706.01789)
	* Unsupervised Deformable Registration: [Link](https://arxiv.org/abs/1704.06065)
* Unsupervised Learning: This is the most urgent thing I want to learn. 
	* A general overview: [link](https://culurciello.github.io//tech/2016/06/10/unsup.html)
	* ~~Insight from Yann LeCunn and the Facebook AI group about adversial network, a new paradigm for unsuperised learning. [link](https://code.facebook.com/posts/1587249151575490/a-path-to-unsupervised-learning-through-adversarial-networks/)~~ and a key paper introducing [DCGAN](http://arxiv.org/abs/1511.06434).  
	* A tutorial on Variational Autoencoder, [paper](http://arxiv.org/abs/1606.05908)
	* A comprehensive tutorial on the concept of "adversarial network", a very promising solution to unsupervised learning. [link](https://ishmaelbelghazi.github.io/ALI/)
* Instance Segmentation using deep learning: performing segmentation on the instance level (maybe one by one in a recurrent framework or in one shot)
	* via deep metric learning, [Link](https://arxiv.org/abs/1703.10277)
	* using recurrent attention, [link](http://arxiv.org/abs/1605.09410)
	* also predicting depth, [link](http://arxiv.org/abs/1604.05096)
	* a recent survey, [link](http://arxiv.org/abs/1602.06541)
	* ~~instance sensitive FCN by Kaiming He~~, [link1](http://arxiv.org/abs/1603.08678) and [link2](http://arxiv.org/abs/1512.04412)
	* using CNN+CRF [(link)](http://www.robots.ox.ac.uk/~tvg/publications/2016/InstanceSegmentation.pdf)
* Combinining with CRF [link1](https://arxiv.org/abs/1412.7062) and [link2](http://arxiv.org/abs/1511.03328)
* ~~ENet: for real-time application [link](https://arxiv.org/abs/1606.02147)~~
* Dealing with high resolution images, [paper](http://arxiv.org/abs/1606.02585v1)
* Image colorization and syhthesis using deep learning:
	* MFR+CNN, [link](http://arxiv.org/pdf/1601.04589v1.pdf)
	* a webpage describing recent works, [link](http://richzhang.github.io/colorization/)
	* deep colorization [link](http://www.cs.cityu.edu.hk/~qiyang/publications/iccv-15.pdf)
	* a recent work [link](http://arxiv.org/pdf/1603.08511.pdf)
* ~~MUST READ: Online hard example mining [(OHEM)](https://arxiv.org/pdf/1604.03540v1.pdf). I have thought about this idea for a long time. It is finally solved.~~ 
* An important paper: Bayesian Deep Learning. [link](http://arxiv.org/pdf/1608.06884.pdf). The key idea is to elaborate a model to unify deep learning and graphical models.
* 3D segmentation:
	* voxResNet: [link](https://arxiv.org/abs/1608.05895)
	* 3d u-net: [link](https://arxiv.org/abs/1606.06650)
	* ~~Recurrent FCN:~~ [link](https://arxiv.org/abs/1608.03974)
* Weakly Supervised Segmentation
	* ~~Point-level supervision for semantic segmentation: [(paper)](http://arxiv.org/abs/1506.02106). I have been seeking an elegant way to utilize point level supervision for a long time. This work provides some good experiments and thoughts. In this paper, however, the labelled points in each image still requires to cover all instance (one point per intance), which is not feasible in certain circumstances.~~   
	* Seed, Expand and Constrain. [link](https://arxiv.org/abs/1603.06098)
* Expressive power of DNN: People may say DNN is able to express very complex non-linear function. But how to quantify such capability? I just found this paper to read. [link](http://arxiv.org/abs/1606.05336) 
* New Schemes for parameter initialization in CNN, two papers in ICLR 2016: [paper1](http://arxiv.org/pdf/1511.06856v2.pdf) [paper2](http://arxiv.org/pdf/1511.06422v7.pdf)
* Weight initialization for RNN. [paper](https://arxiv.org/abs/1511.03771)
* Weight Normalization: a new scheme for better training of CNN. [link](https://arxiv.org/pdf/1602.07868.pdf)
* SqueezeNet: A CNN using much less memory without reducing accuracy. [paper](http://arxiv.org/abs/1602.07360)
* Style transfer [paper](http://arxiv.org/abs/1508.06576) and [code](https://github.com/fzliu/style-transfer)
* Extreme Learning machine, another type of machine learning algorithms which is closers to human brain [review paper](http://www.sciencedirect.com/science/article/pii/S0893608014002214)
* Binary CNN: [paper1](http://arxiv.org/abs/1511.00363) and [paper2](http://arxiv.org/abs/1603.05279)
* ~~Combining CNN with Active Contour: [paper](http://arxiv.org/pdf/1607.05074v1.pdf)~~
* CNN on graphs: Extend classic CNN which applies on grids (e.g., images) to graph data [paper1](http://arxiv.org/abs/1605.05273) and [paper2](http://arxiv.org/abs/1506.05163)
* Inside-Outside Network: A method combining information insider region of interest and outside the region of interest. [(link)](http://arxiv.org/abs/1512.04143)
* A comprehensive comparison of different choices in each component in CNN, such as different activation function or different pooling. [link](http://arxiv.org/abs/1606.02228)
* CNN in convert sketch to image, [link](https://arxiv.org/abs/1606.03073)
* Piecewise Training [link](http://arxiv.org/abs/1504.01013)
* Object detection using R-FCN, [link](https://arxiv.org/abs/1605.06409), [code](https://github.com/daijifeng001/R-FCN)
* Pixel Recuurent Neural Network (best paper in ICML 2016), [link](http://arxiv.org/abs/1601.06759?url_type=39&object_type=webpage&pos=1)
* Edge detection by DNN. [github link](https://github.com/s9xie/hed/blob/master/README.md)
* ~~Densely connected CNN [link](http://arxiv.org/pdf/1608.06993.pdf)~~
* ~~Wide Residual Network [Torch code](https://github.com/szagoruyko/wide-residual-networks),[paper](http://arxiv.org/abs/1605.07146)~~
* Guide to Tensorflow, [link1](https://www.oreilly.com/learning/hello-tensorflow), [link2](https://www.oreilly.com/learning/hello-tensorflow)
* Deep learning and human-in-the-loop. [link](https://blogs.technet.microsoft.com/machinelearning/2016/10/17/the-power-of-human-in-the-loop-combine-human-intelligence-with-machine-learning/)
* Translation aware FCN [link](https://github.com/daijifeng001/TA-FCN)
* How to implement your own layers in Torch7. [link](https://web.archive.org/web/20160104174845/http://code.madbits.com/wiki/doku.php?id=tutorial_morestuff)
* Learning Recursive Filters for Low-Level Vision via a Hybrid Neural Network. [link](http://www.sifeiliu.net/linear-rnn)
* Open problems in AI. [link](http://ai-on.org)
* Depthwise Separable Convolutions. [link](https://arxiv.org/abs/1610.02357)
* Bilateral Solver for edge aware smoothing in deep learing. [link](https://arxiv.org/abs/1511.03296)
* Multiple instance learning in neural network. [link](https://arxiv.org/abs/1610.02501)
* Deep vision tracking benchmark. [link](https://github.com/foolwood/benchmark_results)
* ...





