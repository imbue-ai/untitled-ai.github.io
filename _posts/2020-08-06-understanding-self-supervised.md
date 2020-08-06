---
layout: post
title:  "Understanding the state of the art in self-supervised learning"
date:   2020-08-04 13:38:42 -0400
categories: self-supervised machine-learning contrastive byol batch-norm

author: 
- Abe Fetterman 
- Josh Albrecht
---

# Summary

In this post, we review a few state of the art approaches to self-supervised learning (SimCLR, MoCo, and BYOL) and highlight a surprising finding from our own research: that **batch normalization can cause contrastive learning**. This serves to unify all of these algorithms as alternative approaches to contrastive learning.

# What is self-supervised learning?

Machine learning is the process of optimizing parameters to find the best function that maps from some input data to some output data. Typically this is done in a *supervised* fashion, meaning that both the input data and the output data can be used to optimize the parameters of the function. By contrast, in a *[self-supervised](https://www.notion.so/Blog-Post-Understanding-the-state-of-the-art-in-self-supervised-learning-1fe76be59f184ebeaa7ec63f602ef386#b810e84f307443e4af5aba9983ab03df)* setting no output data is provided.

We generally think of the *output* *data* as the *answers*, so at first this might seem impossible. How can the algorithm learn anything without having answers to learn? Self-supervised learning offers a simple and powerful resolution to this contradiction: use a subset of the input data to predict the rest of the input data. It turns out that this training scheme learns patterns that end up being useful for almost all practical tasks related to that input data!

This approach has proven successful on everything from language to images and audio. In fact, most recent language models, from [word2vec](http://jalammar.github.io/illustrated-word2vec/) to [BERT](http://jalammar.github.io/illustrated-bert/) and [GPT-3](https://arxiv.org/abs/2005.14165), are examples of self-supervised approaches. More recently, this approach has had some incredible results for audio and images as well (starting with works like Contrastive Predictive Coding), and [some believe](https://cacm.acm.org/news/244720-yann-lecun-yoshua-bengio-self-supervised-learning-is-key-to-human-level-intelligence/fulltext) that it may be an important component to human-like intelligence.

In the remainder of this article, we will limit our discussion to some of the most recent state of the art self-supervised algorithms for image data, though the principles apply to other forms of data as well. For more background, see [this](https://deepmind.com/blog/article/unsupervised-learning) DeepMind blog post, [this](https://www.fast.ai/2020/01/13/self_supervised/) practical overview from FastAI, or [this](https://lilianweng.github.io/lil-log/2019/11/10/self-supervised-learning.html) in-depth post on everything related to self-supervised learning and representation learning. [This github repo](https://github.com/HobbitLong/PyContrast/blob/master/AWESOME_CONTRASTIVE_LEARNING.md) contains a number of other relevant papers as well.

# The state of the art in self-supervised learning

Up until a few months ago, the highest performing self-supervised algorithms for learning image representations were [MoCo](http://arxiv.org/abs/1911.05722) and [SimCLR](http://arxiv.org/abs/2002.05709), which are both examples of what is typically called *contrastive learning*. Contrastive learning roughly works by training a classifier to distinguish between similar and dissimilar input data. In both MoCo and SimCLR, positive examples are augmented (transformed) versions of the same image, while negative examples are augmentations (transformations) of other images.

A recent work by Grill, Strub et. al., titled [Bootstrap Your Own Latent](http://arxiv.org/abs/2006.07733) (BYOL), introduces an algorithm for self-supervised learning of image representations that exceeds the performance of both SimCLR and MoCo. Where MoCo and SimCLR use contrastive learning between positive and negative examples in their loss functions, BYOL uses only positive examples in the loss function.

At first glance, it appears that BYOL is learning without explicitly contrasting between multiple images. **Surprisingly however, we find that BYOL is not only doing contrastive learning, but that contrastive learning is required for it to learn**. We will first review how these algorithms work before we get into the details of our experiments.

### SimCLR

SimCLR is a particularly simple self supervised algorithm. Two [augmentations](https://www.notion.so/Blog-Post-Understanding-the-state-of-the-art-in-self-supervised-learning-1fe76be59f184ebeaa7ec63f602ef386#519cbff8227c4638be369af6a7e91fdc) *v* and *v'* of the same image *x* are fed through the same network to produce two projections *z* and *z'*. The contrastive loss aims to maximize the similarity of the two projections from the same input *x*, while minimizing the similarity to projections of other images within the same minibatch. The multilayer perceptron (MLP) used for projection in SimCLR uses batch norm after each linear layer. (See the appendix for a table that shows the notation used in each of the papers. In this post we use the notation from BYOL for consistency.)

![SimCLR diagram](/assets/img/understanding_self_supervised/Screen_Shot_2020-07-15_at_4.39.44_PM.png)

SimCLR architecture.

### MoCo

Unlike SimCLR, where the top and bottom row in the diagram represent the same network (parameterized by $\theta$), MoCo splits the single network into an *online network* (top row) parameterized by $\theta$ and a *momentum network* (bottom row) parameterized by $\xi$ . The online network is updated by stochastic gradient descent, while the momentum network is updated based on an exponential moving average of the online network weights. The momentum network allows MoCo to efficiently use a memory bank of past projections as negative examples each time the contrastive loss is calculated. The new projections *z'* are used as positive examples. The MLP used for projection in [MoCo v2](http://arxiv.org/abs/2003.04297) does not use batch normalization.

![MoCo diagram](/assets/img/understanding_self_supervised/Screen_Shot_2020-07-15_at_4.40.22_PM.png)

MoCo v2 architecture. Top row is online encoder, bottom row is momentum encoder.

### BYOL

BYOL builds on the momentum network concept of MoCo, adding an additional MLP $q_\theta$ to predict z' from z. Rather than using a contrastive loss, BYOL uses the L2 error between the normalized prediction p and target z'. Because negative examples are not required for this loss function, the there is no memory bank in BYOL. Both MLPs in BYOL use batch normalization after the first linear layer only.

![BYOL diagram](/assets/img/understanding_self_supervised/Screen_Shot_2020-07-28_at_1.56.15_PM.png)

BYOL architecture.

# Surprising Results

We originally implemented BYOL in PyTorch using code we had written for MoCo. When we began training our network, we found that **the network performed no better than random**. Comparing our code to [another available implementation](https://github.com/sthalles/PyTorch-BYOL) (thanks sthalles!), we discovered we were missing batch normalization in the MLP. We were quite surprised that batch normalization was critical to training BYOL, while MoCo v2 did not require it at all.

For our initial testing, we trained a ResNet-18 with BYOL on the STL-10 unsupervised dataset using SGD with momentum and a batch size of 256. Below are the first ten epochs of training for the same BYOL algorithm with and without batch normalization in the MLPs

![Linear evaluation accuracy on STL10](/assets/img/understanding_self_supervised/Screen_Shot_2020-07-28_at_11.01.07_AM.png)

Linear evaluation accuracy on a validation set during early training of a ResNet-18 on STL10. When BYOL is trained without batch normalization in the MLP, the performance remains no better than a random baseline.

## Digging in for more data

In order to investigate the cause of this dramatic change in performance, we performed a number of additional experiments. 

![Contrastive Loss Diagram](/assets/img/understanding_self_supervised/Screen_Shot_2020-07-27_at_6.44.04_PM.png)

Configuration used for experiments with contrastive loss, enabling better comparison to BYOL results.

We first tried to confirm that the BYOL style network *without* batch normalization and *with* the projection MLP *q* would indeed learn useful representations with a contrastive loss function (see above figure). We found that the network was able to perform significantly better than random within ten epochs. This indicated to us that there is something about **not using a contrastive loss function** that is causing the dependence of training on batch normalization.

We then wanted to find whether another type of normalization would have the same effect. We applied [Layer Normalization](https://arxiv.org/abs/1607.06450) to the MLPs instead of batch normalization, and trained the network with BYOL. As in the experiments where MLPs had no normalization, the performance was no better than random. This tells us that the **activations of other inputs in the minibatch** are essential in helping BYOL find useful representations.

Next, we wanted to know whether batch normalization is required in the projection MLP $g$, the prediction MLP $q$, or both. Our experiments show that batch norm is most useful in the projection MLP, but the network can learn useful representations with batch normalization in either MLP. A **single batch norm layer** in one of the MLPs is sufficient for the network to learn.

[Performance of experiments for comparison](https://www.notion.so/2785d60fa500433f8db14b286cdba8bf)

To summarize the findings so far: there is something about a single batch norm layer related to the activations from other inputs in the minibatch that is necessary for BYOL training to be successful without a contrastive loss function.

One purpose of negative examples in the loss function is to prevent *[collapsed representations](https://www.notion.so/Blog-Post-Understanding-the-state-of-the-art-in-self-supervised-learning-1fe76be59f184ebeaa7ec63f602ef386#fac40a11f1c741c6b2a09620e181c672)*. An example of a collapsed representation would be a network that always outputs [1, 0, 0, 0, ...] as its projection vector *z*. One can see that with this representation, if the network can learn the identity function for $q$, it can achieve perfect prediction accuracy.

The importance of batch normalization becomes clearer in this context. If batch normalization is used in the projection layer $g$, the projection output vector *z* cannot collapse to any singular value like [1, 0, 0, 0, ...] because that is exactly what batch normalization prevents. However similar the inputs to the batch normalization layer are, the outputs will be redistributed according to the learned mean and standard deviation.  **Representation collapse is prevented precisely because all samples in the minibatch cannot take on the same value after batch normalization**. 

A similar effect is introduced by batch normalization in the prediction MLP. The function $q$ cannot learn the identity function if the minibatch inputs are very similar: the batch norm will redistribute the activations through vector space, so that the final layer predictions are all very different. This function will only be successful at predicting projection vectors z' if those vectors z' are sufficiently well separated in representation space (that is, not collapsed), because the predictions p are constrained to be well separated across the minibatch.

Our findings seem consistent with a simple conclusion: to prevent mode collapse we must be able to identify the common mode between examples. Batch normalization identifies this common mode between examples of a minibatch and removes it — using those other representations as **implicit negative examples**. We can see this as a novel way of implementing contrastive learning on embedded representations.

## Representation similarity

To test our intuition that representation collapse is being prevented by batch normalization, we measured the cosine similarity of the first input projection vectors $z$ with the second input projection vectors $z^\prime$ after the training each of the variants above. We measured the average cosine similarity between the projections of positive examples (in blue), as well as the similarity to the projections from negative examples from the same minibatch (in red) over each minibatch in the tenth epoch of training. 

For normal BYOL training, we see the projections are more similar between the positive examples (0.88) than between negative examples (0.27). However, with no batch normalization in $g$ or $q$, the projections are highly aligned with both positive and negative examples (0.9999), indicating a collapse of the representation to a common vector. Because layer normalization does not introduce contrastive learning, it also results in aligned positive and negative representations.

![understanding_self_supervised/Screen_Shot_2020-07-28_at_10.50.27_AM.png](/assets/img/understanding_self_supervised/Screen_Shot_2020-07-28_at_10.50.27_AM.png)

The average cosine similarity between the projections *z* and *z'.* The lower (blue) bar is the similarity between projections of the same image *x*, while the upper (red) bar is the similarity between projections of different images in the same minibatch. The high similarity of all representations for the no MLP normalization experiment and the layer normalization experiment indicates representation collapse.

These results support our understanding of batch normalization as implicitly introducing contrastive learning using minibatch statistics.

# Conclusion

We found it quite interesting that even without negative samples in the loss function, batch normalization implicitly introduced contrastive learning in BYOL. In retrospect, this discovery is not actually all that surprising — obviously there is no learning when there is mode collapse, and you cannot detect or prevent mode collapse without knowing the mode! Whether you're contrasting different images with each other, or you're contrasting each image with the average of all images, **learning is precisely about understanding how things differ from each other.**

Besides shining a light on how batch norm works in contrastive learning, this may serve as a lesson in how batch normalization can have unexpected side effects. With batch normalization, the network outputs are no longer learning a pure function of the corresponding inputs. For this [and other reasons](https://www.alexirpan.com/2017/04/26/perils-batch-norm.html), we suggest other practitioners be careful about using batch normalization in training, and should perhaps default to alternatives like layer norm or [weight standardization with group norm](https://arxiv.org/abs/1903.10520).

Of course, the opposite is an interesting avenue for future work as well. Rather than avoid batch normalization because of this implicit contrastive effect, it may be interesting to exploit that directly. Because the batch norm can operate on representations other than the final layer, it may be also be a useful tool to use in conjunction with contrastive loss functions, or where internal representation collapse is a potential issue. An interesting question is whether this separation of internal representations contributes to batch norm's success in training neural networks

With the rapid progress self-supervised learning is going through right now, new state of the art algorithms are sure to be published soon. Please share with us any new results you think are relevant to our research here. In addition, if something looks incorrect, or you have questions about our experiments, don't hesitate to reach out and contact us.

# Footnotes

[1] *unsupervised* is sometimes used interchangeably with *self-supervised*, though as Yann LeCun points out [here](https://www.facebook.com/722677142/posts/10155934004262143/), the term *unsupervised* is both loaded and confusing.

[2] *collapsed representations* is used with the same meaning in the BYOL paper (section 3). Other practitioners may identify the phenomenon as *mode collapse*. 

# Appendix

The BYOL terminology is used throughout this blog post. To compare to other papers, see the below table.

[Terminology Comparison](https://www.notion.so/cab0de65036042079f177315b13d2894)

## Applied Augmentations

The transforms used are, using `torchvision.transforms`, with inputs `crop_size=96` and `s=0.5`, the color jitter strength:

```python
Compose([
  RandomResizedCrop(crop_size, scale=(0.2, 1.0)),
  RandomApply(
    [ColorJitter(0.8 * s, 0.8 * s, 0.8 * s, 0.2 * s)], p=0.8
  ),
  RandomGrayscale(p=0.2),
  RandomHorizontalFlip(),
  RandomApply([GaussianBlur([0.1, 2.0])], p=0.5),
  ToTensor(),
  Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
])
```

The `GaussianBlur` function applies blur with a radius chosen randomly from the uniform distribution [0.1, 2.0].