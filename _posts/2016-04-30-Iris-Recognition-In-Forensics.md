---
layout: post
title:  "Iris Recognition In Forensics"
date:   2016-04-30
excerpt: "An iris recognition approach based on the detection and matching of iris crypts. This new method, mimicing fingerprint identification, allows human to supervise the procedure and exercise judgement."
project: true
comments: true
---

# Iris Recognition In Forensics 

I developed an iris recognition method based on detecting and matching of human interpretable features (i.e., crypts, as shown below), which can be seamlessly integrated into [the human-in-the-loop iris recognition framwork]((http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=6835998)) proposed by Feng Shen and Prof. Flynn. 

***
The source code is available [HERE](http://ott.nd.edu/software-available-for-license/iris-recognition-based-on-human-intrepretable-features/) for academic use only. Please email me (jchen16@nd.edu) for the download authorization code. 

***

<img src="{{ site.url }}/pic/iris_crypt.png" alt="crypt" style="width: 600px;">

### Motivation:
In law-enforcement applications, iris is a (arguablly) less well-established biometric trait than fingerprint. Classic iris recognition algorithms work as a black-box: images in and scores out. One possible way to promote iris recognition in the field of forensics is to make the identification procedure visible and interpretable to human, just like fingerprint matching, and so that human experts can excercise judgement in making the final decision. It has been shown that iris crypts can work just like minutia on fingerprints ([paper](http://proceedings.spiedigitallibrary.org/proceeding.aspx?articleid=1693595)).


### Methodology

The approach consists of two steps: segmentation and matching. 

The proposed iris crypts segmentation algorithm takes as input the unwrapped iris sheet and generates a binary mask of the same size containing detected crypts. The algorithm applys a morphological operation in a hierarchical manner, illustrated as follows. 

<img src="{{ site.url }}/pic/iris_segmentation.png" alt="segmentation" style="width: 650px;">

To match the detected crypts accross different images, we used the matching model based on Earth Mover's Distance, which I primarily developed for matching cells accrossed consecutive frames. See this [post] for details.

One example is shown below. The matched crypts are displayed in the same color. The red windows indicate some topological changes in the detected crypts. Our matching model is shown to be able to handle such topology variation to make a reliable matching.

<img src="{{ site.url }}/pic/iris_matching.png" alt="matching" style="width: 500px;">



### Source Code

The source code is released through the Office of Technolgy Transfer at the University of Notre Dame. [Download](http://ott.nd.edu/software-available-for-license/iris-recognition-based-on-human-intrepretable-features/)

### References
*  Jianxu Chen, Feng Shen, Danny Z. Chen, and Patrick J. Flynn. "Iris recognition based on human-interpretable features." IEEE Transactions on Information Forensics and Security, vol. 11, no. 7, pp. 1476-1485, 2016
*  Jianxu Chen, Feng Shen, Danny Z. Chen, and Patrick J. Flynn. "Iris recognition based on human-interpretable features." In Proc. IEEE Conference on Identity, Security and Behavior Analysis (ISBA), pp. 1-6, 2015.