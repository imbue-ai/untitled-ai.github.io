---
layout: post
title:  "A PyTorch Implementation of Slot Attention"
date:   2021-02-11 09:00:00 -0700
category: machine-learning
tags: unsupervised machine-learning open-source  

author: 
- <a href="https://brydenfogelman.com/">Bryden Fogelman</a> (<a href="mailto:bryden1995@gmail.com">email</a>)
---

TL;DR: We’re open sourcing a PyTorch Implementation of one of our favorite papers ([Object-Centric Learning with Slot Attention](https://arxiv.org/abs/2006.15055)) from [NeurIPS 2020](https://neurips.cc/). 


You can checkout our implementation at [https://github.com/untitled-ai/slot_attention](https://github.com/untitled-ai/slot_attention).

{% include image.html 
url="/assets/img/slot_attention/slot_attention_results.png" 
alt="Slot Attention" 
caption="Outputs of our slot attention model. This image demonstrates the models ability to divide objects (or parts of objects) into slots."
%}

<!--more-->

### Why we chose this paper:

As a human looking at the image above, we can almost immediately pick out the separate objects in the image. By contrast, 
machine learning models have a surprisingly difficult time understanding which pixels constitute “an object” by human standards. 
While there has been a lot of success in training supervised models to complete this task [^1], 
it’s largely unsolved with unsupervised models [^2]. To solve complex tasks that humans can do, it’s 
important that our models actually <i>understand</i> what objects are.

One of the most interesting things about Object-Centric Learning with Slot Attention is that it introduces a novel way to 
decouple objects from the original input without any training or supervision, as shown by the results in figure X. The model 
does this by forcing “slots” to compete over different features of the original image. The mechanism used to enable this 
competition is similar to the attention mechanism popular in other domains of machine learning [^3]. It’s exciting 
that unsupervised models can now determine objects from complex scenes, and can even do so without using depth, motion, 
or other helpful signals.

### What’s next?

While slot attention is a step in the right direction, there are plenty of interesting open questions. Can this work on real 
data and not toy datasets? What if we had determined objects in an image based on what they’re doing (ie. moving vs static)? 
Instead of reconstruction loss, could we use a contrastive loss instead (checkout this related work by [Sindy Löwe](https://loewex.github.io/) [here](https://arxiv.org/pdf/2011.10287.pdf))?

By reimplementing this paper and sharing our code, we hope we can allow others to help answers these questions and more. 
Note: we weren’t able to full reproduce the result of the paper due to time and GPU constraints, so drop a ticket on our Github 
page if you have any issues. If you have thoughts on the model, where you think it’d be useful, etc., 
please shoot us a note at <a href="mailto:josh@generallyintelligent.ai">josh@generallyintelligent.ai</a>, we’d love to chat!

PS we’re hiring. Checkout out our job postings here or hit us up at <a href="mailto:jobs@generallyintelligent.ai">jobs@generallyintelligent.ai</a>.

### Sources

1. Object-Centric Learning with Slot Attention, [https://arxiv.org/abs/2006.15055](https://arxiv.org/abs/2006.15055).

2. Slot Attention in Tensorflow, [https://github.com/google-research/google-research/tree/master/slot_attention](https://github.com/google-research/google-research/tree/master/slot_attention).

### Footnotes

[^1]: A similar supervised approach to this problem is semantic segmentation. This task involves grouping pixels of an image together that belong to the same object or entity. This means every pixel in the image is labelled with a class that corresponds to a specific object. See more [here](https://paperswithcode.com/task/semantic-segmentation). 

[^2]: Getting labelled data is expensive and time consuming. We also believe that in order for a model to truly generalize it will need more labelled data than we can produce. Unsupervised learning would circumvent this need.

[^3]: This attention mechanism mentioned here was introduced in [Attention Is All You Need](https://arxiv.org/abs/1706.03762).
