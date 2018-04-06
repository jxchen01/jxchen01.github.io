---
layout: post
title:  "Elementwise Loss Pytorch"
date:   2017-09-06
excerpt: "A guide for implementing elementwise loss in pytorch. Elementwise loss refers to assign different weight for different pixel/voxel in the image when calculating the loss."
tag:
- Deep Learning Programming
- Python
comments: true
---


# Elementwise Loss Pytorch


### What is Elementwise loss

The basic idea is to assign different weight for different pixel/voxel in the image when calculating the loss. An example is the loss used in [U-Net] (https://arxiv.org/abs/1505.04597), namely different pixels are of different importance.

### Custom Loss in Pytorch

There are some good resource to learn about custom loss i Pytorch:

* [A simple example in jupyter notebook](https://github.com/Spandan-Madan/A-Collection-of-important-tasks-in-pytorch)
* [A informative discussion on pytorch forum](https://discuss.pytorch.org/t/build-your-own-loss-function-in-pytorch/235/30)

The core idea is to perform all your custom computation using the methods provided for torch tensor, and decorate them with Variable. 

### Elementwise NLL Loss in Pytorch 

class ElementNLLLoss(torch.nn.Module):
	def __init__(self):
		super(ElementNLLLoss,self).__init__()
	
	def forward(self, input, target, weight):

        # input is N-by-3, where 3 is the number of classes
        # target is N-by-1
        # weight is N-by-1
        
		target_np = target.cpu().data.numpy()
		target_np = target_np.astype(int)

		row_num = target_np.shape[0]
		mask = np.zeros((row_num,3)) #### number of classes
		mask[np.arange(row_num), target_np]=1
		class_x = torch.masked_select(input, Variable(torch.from_numpy(mask).cuda().byte()))
	
		out = torch.mul(class_x,weight)
		loss = torch.mean(torch.neg(out),0)

		return loss

### Extra Bonus: Paralle Criteria

Sometimes, we may want to apply multiple criteria with a same ground truth, each on a different output from the model, such as (the deep supervision in cumed-net)[https://www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/view/11789]. Previously, in Torch, this has to be done via (Parallel Criteria)[https://github.com/torch/nn/blob/master/doc/criterion.md#nn.ParallelCriterion].

In Pytorch, this is super easy:

```python
optimizer.zero_grad()

outputs = model(inputs)
loss = criterion(outputs[0], targets) + 0.5*criterion1(outputs[1], targets) + 0.5*criterion2(outputs[2], targets)

loss.backward()
optimizer.step()
``` 