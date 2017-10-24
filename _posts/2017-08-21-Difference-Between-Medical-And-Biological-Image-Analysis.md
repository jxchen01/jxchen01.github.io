---
layout: post
title:  "Difference Between Medical And Biological Image Analysis"
date:   2017-08-21
excerpt: "I have been using the word, Biomedical Image Analysis, for a long time. But, I only have some sense of the difference between biological and medical images, in the context of image analysis."
tag:
- MISC
comments: true
---

# On the Difference Between Medical and Biological Image Analysis

I have used the work "biomedical image analysis" as one of my research areas. But, I don't really thought about what is "bio-" and what is "medical" image analysis before.  In this post, I will try to present my understanding of the difference.

First of all, by medical images, I mean CT, MRI, PET, PET-CT, Ultrasound, X-Ray, etc. [[Ref](http://www.medicalimaging.org/about-mita/medical-imaging-primer/)] and biological images usually refer to all kinds of microscopy images ([Ref](https://youtu.be/01v2kR8dlnQ) and make sure you check out this cool [website](https://www.ibiology.org/)).

To my understandin medical images are acquired to "peak through", while biological images are aiming to "zoom in". No matter it is a CT scan of your chest, or an MRI image of your brain, doctors use such images to peak through your body to make medical diagnosis. On the other hand, biologists want to leverage the powerful microscopy, no matter a tranditional brightfield or advanced light sheet, so that human can zoom in to the micro-world. Natually, biological images and medical images are roughly working on different scales, microns and inches, respectively. 

### What really matters to the image analysis algorithm

#### Variance

Both biological images and medical images suffer from "variance", but in different context. (To clarify, we are not talking about the variance in a large population, but the variance of the images acquired from the same objects.) 

The variance in biological images, especially in live imaging, comes from the dynamic of the objects. Here, "dynamic" may refer to physcial movement or biological development (e.g. cell mitosis), or chemical changes (e.g., fluroscent decay). So, in other words, it is hard to reproduce the same, or even similar, images of the same objects. But, for medical images, theorectically, this is possible. You can take the x-ray of your arm twice and get nearly identical images. (Certainly, this is not common in practice.) 

The variance of medical images comes from multi-modality, where a special research area arises: multimodal image registration [[Ref](https://uncch.pure.elsevier.com/en/publications/learning-based-multimodal-image-registration-for-prostate-cancer-)], and also long-term development, where another specific research area is born: logitudinal image registration [[Ref](https://link.springer.com/chapter/10.1007/978-3-319-10581-9_1)]. Well, biological images also have "multimodal" issues, like images from both ligh channel and fluorescence channel. But, usually, such multi-channel images have much less trouble in terms of registration, because they are usually acquired at very close time points.  

#### Algorithm Generality and Robustness 

As the results of variance, the algorithms designed for biological and medical images sometimes requires different consideration, in terms of generality and robustness. For medical image analysis algorithms, the issue needs to worry most is the anatomy robustness. Namely, you may face very rare images when the patient suffers from certain disease, which may cause significant trouble to the image analysis algorithm, no matter for segmentation or detection, which was designed without or with very limited aware of such rare characteristics. On the other hand, for biological images, the imaging condition plays a critical role. When images are acuqired in different microscopes, under different imaging settings, or when objects are labeled with a different batch of dyes, the image analysis algorithms may generate terribly embrassing results. This becomes an even more severe issue for deep learning models trained on limited amount data.

#### Resolution and Artifacts

A big challeng in the biological images is to fight against limited resolution and different types of artifacts (buzz words: noise, shading, photobleaching, point spread function, diffraction ...). So, image processing techniques, like background removal, shading correction, smoothing, etc., are very important pre-processsing steps are still being actively studied. In contrast, medical images, especially those radiation based, suffer from less artifacts amd usually come with sufficient resolution (mainly due to the imaging resolution and object size are of different scale), even though pre-processing, such as smoothing, contrast enhancing, etc., is still needed in certain situations. One exception is ultrasound image, especially for those newly developed portable devices. 



### Other Related Imaging Modalities

There are other related images in the biomedical domain. For example, the histopathological image is an important one. It is becoming more and more important actually with the fast development of deep learning, since deep neural network based algorithms are able to solve lots of histopathological image analysis problems where conventional methods had very poor performance. Another example is neuronal images (e.g., fluroscent, brightfield, or more commonly electron microscopy), which may also be broadly classified into the "bio-" category, but have very special morphological features.










