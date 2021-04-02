---
layout: post
title:  "Generally Intelligent #9: Drew Linsley, Brown, on inductive biases for vision and generalization"
date:   2021-04-01 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)
- <a href="https://twitter.com/lukelivesfree"> edited by Luke Cheng </a>

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-9-Drew-Linsley--Brown--on-combining-human-visual-biases-and-computer-vision-eu2cm2" width="100%" frameborder="0" scrolling="no"></iframe>>

<br>

Drew Linsley [(Google Scholar)](https://scholar.google.com/citations?user=cXZlAuQAAAAJ&hl=en) [(Website)](https://sites.brown.edu/drewlinsley/) is a Paul J. Salem senior research associate at Brown, advised by Thomas Serre. He is working on building computational models of the visual system that serve the dual purpose of (1) explaining biological function and (2) extending artificial vision. Prior to his work in the Serre lab, he completed a PhD in computational neuroscience at Boston College and a BA in Psychology at Hamilton College.

His most recent paper at NeurIPS is [Stable and expressive recurrent vision models](https://serre-lab.github.io/crbpsite/).  It presents an alternative to back-propagation through time (BPTT) for recurrent vision models called "contractor recurrent back-propagation" (C-RBP), which has O(1) complexity for an N step model vs. O(N) for BPTT, and which learns long-range spatial dependencies in cases where BPTT cannot.  

Drew is also organizing an ICLR 2021 workshop named [Generalization Beyond the Training Distribution in Brains and Machines](https://iclr2021generalization.github.io/) on Friday, May 7th, 2021. Find them on the website and @ICLR_brains.

Lastly, Drew is looking to work with collaborators in robotics, so feel free to reach out!


**Highlights from our conversation:**

🧠 Building brain-inspired inductive biases into computer vision

🖼 A learning algorithm to improve recurrent vision models (C-RBP) 

🤖 Creating new benchmarks to move towards generalization

<br>

### Some quotes we loved
> **[06:35] Drew’s work over the past five years:** 
“And so over the past five years, I think we've put together a pretty interesting theory, through several papers, on how understanding the brain and circuits in the brain specifically can help us build better artificial intelligence.  The crux of this theory is that the biases in vision represent heuristics, essentially shortcuts taken by the brain, which are shaped by the statistics of the visual world, of our visual surroundings. And so when you imbue an artificial model of vision with such shortcuts, what you get as a by-product is a whole host of really interesting phenomena emerging. So one, you get is what's known as sample efficient learning.  Two, you can have better generalization - better generalization to low level noise that may be added to images, than a model without such biases. Then third, the way we implement these biases is through what are called recurrent models. What's cool about that is essentially you get this ability to generalize, to what's commonly known in the field of computer vision, artificial intelligence as domain shifts.  So you can generalize to examples which are completely novel in a sense to the training set.”

> **[09:25] Understanding the brain and biases to help build AI systems:** 
“What I believe is that by understanding how the brain works... 
>
> And the understanding, I think needs to be at two levels first.  By building computational theory, which you can say at a cognitive level of how we process sensory inputs, how we learn from those inputs and how we learn and convert those inputs into memory, and then how we form decisions based off of our inputs - all of these different cognitive level descriptions of intelligence are central to developing theory for what is the desired way of learning and developing intelligent systems. But then too, I think if you work at the level of circuits - and so what this means is at the level of inhibitory and excitatory cells and how those connect together and shape processing of inputs - if you link those two levels of analysis together, then I think what you can get is some interesting biases, which align with biological intelligence.  
>
> And as a result, you're essentially building inductive biases into your artificial intelligence systems...
>
> Why would we have all these biases? You start to look into biological intelligence and you see these all over the place, in working memory, in decision-making.”

> **[18:59] How AI can help neuroscience:**
> "The by-product of (identifying biases for AI systems), of looking to biology and embedding those concepts into your artificial intelligence systems is that you can also contribute to neuroscience. You can start to screen for these various mechanisms and their importance in intelligence, intelligent behavior."

> **[10:47] Biases we would not think of:**
“Now, the reason why I think it's important to look to the brain. It’s because there's no way that an engineer would sit down and think that it's good to have an illusion.”

> **[15:21] Inductive biases vs. just scaling up:**
> It goes back to this broader question of what is the right way forward.  I think the biggest breakthroughs in AI over the past several years have been from companies like OpenAI which adopts a distinctly different viewpoint towards research than I do…  With infinite scale, what can you accomplish? That is the hypothesis that I think companies like OpenAI are testing and it's a valid way. It's good that they're testing it.  The proof is in the pudding, GPT-3 is unbelievable as are their new vision models.
>
> The question is, do you want to spend all of your resources pursuing this huge data, no bias model approach, or do you want to maybe identify some of the important biases adopted by intelligence systems for navigation, decision making vision, etc. - those that will help you in artificial intelligence.

> **[21:07] Hmax model and the brain:**
> “Hmax is a really important model.  It was the initial hierarchical network model.   And then Tomaso Poggio and Maximilian Riesenhuber used this model to generate hypotheses about how hierarchical processing works in the brain.” 


> **[47:56] How their model improves upon classic CNNs in segmentation benchmarks:**
> “For our model, I think in general what we found is qualitatively you would suppress some of the false positives that you get from the standard FPN network. If you look at the development of our models, because we can look at the time course of their segmentation, it will have false positives early in the time course, but sometimes sometimes those get overridden, whereas the feed forward model is fixed.”  

> **[52:32] Synchrony of neurons:**
> “I don't have this theory, but I do want to mention that there's some really interesting work from Thomas, my advisor, on synchrony. There's this concept of neurons firing together or not based on some information about stimuli. And so this is like an emergent phenomenon called synchrony which is recorded in brains by neuroscientists.”

> **[53:37] Spatial temporal vision:**
> “A key problem in the field right now is spatial temporal vision.  The way this is typically done is you expand your 2d convolutional model into a 3d one. So you add another dimension to your kernels which is just going to be hopefully encoding for some dependency between frames of the input...
>
> I think what was happening is that these data sets are relatively easy to recognize based only on static frames. So action recognition is turned into a 2d frame recognition problem, but the task of motion processing, I think, is absent from these models.”

> **[56:48] Building new benchmarks:**
> “So the hypothesis that I'm testing right now with some colleagues is whether we can build recurrent models, which I think is a much more natural fit for the spatial temporal domain, that can encode appropriate features - both tuned and untuned spatial temporal features. Now where it's going to be difficult is once again competing with the state of the art, because the field has a way of hyperparameter optimizing over the architectures that work best on specific data sets. 
>
> So what does that say? We're definitely using the wrong benchmarks and so there's always going to be an interest in developing more naturalistic tasks. But what's the ecological task for motion recognition?  I don't know.  I've started to work with colleagues on game playing (similar to OpenAI’s ProcGen).”

<br>

### Show Notes

* Intro [01:22]
* Drew Linsley’s work & upcoming workshop [02:09]
* How Drew got into the field [02:42]
* The major theories Drew has been working on [06:35]
* How understanding the brain can help us build intelligent systems [09:22]
* The colored dress as an open research question on color perception bias [11:09]
* Drew’s paper on contextual illusions for contour detection -  [Recurrent neural circuits for contour detection](https://openreview.net/forum?id=H1gB4RVKvB)  [11:51]
* Using models of biological phenomena in computational neuroscience to look for mechanistic explanations [13:19]
* Biological intelligence and its unintuitive methods (illusions) [13:56]
* Kanjun’s quick summary up until this point in the podcast [14:42]
* What’s the right way forward for neuroscience and AI? [15:21]
* Stuart Geman, statistical learning theory, the bias variance tradeoff and how it relates to strategies in AI [16:14]
* Limitations of hardware driving software development and vice versa [19:30]
* How does Drew pick which biases are important to work on or explore? [20:28]
* Hmax and preattentive processing vs. attentive processing [20:53]
* Pathfinder, a dataset with tasks that transformers cannot solve (yet) [26:40]
* Top-down feedback for feed forwards models (like a CNN) [30:40]
* JK and Drew’s paper for top-down feedback -  [Disentangling neural mechanisms for perceptual groupings](https://arxiv.org/abs/1906.01558#:~:text=Forming%20perceptual%20groups%20and%20individuating,top%2Ddown%20connections%20between%20neurons.)  [32:28]
* The importance of aligning tasks in your experiment to a specific model hypothesis [34:29]
* Drew’s summary on how they’ve looked at biases step-by-step in the visual system [35:41]
* Drew’s 2020 NeurIPS paper,  [Stable and expressive recurrent vision models](https://arxiv.org/abs/2005.11362)  [37:01]
* The performance of computer vision models on Panoptic Segmentation [47:02]
* What prompted Drew to pursue his hypothesis on recurrent visual models? [49:26]
* Pet theories - theories without much data or evidence [51:42]
* Thomas Serre’s theory about the synchrony of neurons [52:32]
* Motion models and spatial temporal models [53:15]
* Hyper-optimization and how it could be holding the field back [57:07]
* Which of Drew’s work might be overlooked? (2019 ICLR paper -  [Learning what and where to attend](https://arxiv.org/abs/1805.08819) ) [59:34]
* Emergent and bi-stable images, potential useful biases for machine vision [1:03:56]
* More of, what might be holding the field back? (getting the right benchmarks) [1:06:32]


<br>

*The full transcript is coming. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
