---
layout: post
title:  "Generally Intelligent #8: Giancarlo Kerg, Mila, on approaching deep learning from mathematical foundations"
date:   2021-03-26 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-8-Giancarlo-Kerg--Mila--on-approaching-deep-learning-from-mathematical-foundations-etk3ep" width="100%" frameborder="0" scrolling="no"></iframe>

<br>

Giancarlo Kerg [(Google Scholar)](https://scholar.google.ca/citations?user=GcJkks8AAAAJ&hl=en) is a PhD student at Mila, supervised by Yoshua Bengio and Guillaume Lajoie.  He is working on out-of-distribution generalization and modularity in memory-augmented neural networks.  Prior to his PhD, he studied pure mathematics at Cambridge and Université Libre de Bruxelles. 

His most recent paper at NeurIPS is [Untangling tradeoffs between recurrence and self-attention in neural networks](https://arxiv.org/abs/2006.09471).  It presents a proof for how self-attention mitigates the gradient vanishing problem when trying to capture long-term dependencies. Building on this, it proposes a way to scalably use sparse self-attention with recurrence, via a relevancy screening mechanism that mirrors the cognitive process of memory consolidation.

**Highlights from our conversation:**

🧮 Pure math foundations as an approach to progress and structural understanding in deep learning research

🧠 How a formal proof on the way self-attention mitigates gradient vanishing when capturing long-term dependencies in RNNs led to a relevancy screening mechanism resembling human memory consolidation

🎯 Out-of-distribution generalization through modularity and inductive biases

🏛 Working at Mila with Yoshua Bengio and other collaborators

<br>

### Some quotes we loved
> **[06:03] Benefits of mathematical rigor in deep learning:**
“I felt like the field was lacking a little bit more of mathematical understanding.  A lot of people are just running a lot of random experiments and there's a lot of hyper parameter tuning. Sometimes, you just don't really have a feeling of what is going on.  You just try what works blindly.  Sometimes I feel a lack of structural understanding of certain things.  It definitely needs more rigor in some aspects.  Sometimes people think of mathematics as almost useless.  We need the rigor. We need math in deep learning. It's just very hard to apply sometimes because we don't really know what the gradient is doing but making an effort to incorporate mathematics will, I think, have great benefits to deep learning.” 

> **[07:27] The idea of his most recent NeurIPS paper:**
“The paper was Yoshua’s idea. He had this idea of proving that we mitigate gradient vanishing in self-attentive recurrent neural networks.  It's supposed to provide a guarantee that I have something that I think was common knowledge, but a clear, rigorous understanding of all the edge cases. When does it break down and how can we sparsify self-attention? To what extent and how, so that the grading propagation is still beneficial. 

> **[09:36] Sparse attention in humans:**
“Humans, they also have these sparse attention.  We can remember things from childhood. How are we able to do so?  How are we able to do credit assignment over extremely long timescales?  So we must sparse attention into the past.  How can we implement that in such a way that we have some type of computationally effective way to deal with attention and at the same time also get this gradient propagation?  

> **[10:18] Relevancy screening mechanism, as an analog to memory consolidation:**
“We developed a screening mechanism where we go from quadratic computational complexity of self attention into linear computational complexity.  We consider a fixed time horizon where we compute some type of relevancy score for a given state.  And then by a simple heuristic, we decide whether we should keep this state in memory or not, but over a very fixed time horizon. The funny thing now is that in hindsight, it actually resembles the process of memory consolidation, which is the transfer of memory tokens from short-term to long-term memory.

> **[19:30] Competition as a method for building inductive biases:**
“What inductive biases does the brain use to generalize out of the submission?  It seems a lot of neurons are cooperating in some way to have this effect.  It's believed somehow that this happens through competition bits of information or neurons...  This is one inductive bias that really fascinates me. I want to understand more.”

> **[21:24] Bottom-up vs top-down mechanisms in humans and in ML (BRIMS):**
“In neuroscience, we have this bottom-up perception and the top-down is basically what you believe to be true - the prior beliefs. When the bottom-up signal is ambiguous, you auto-complete with a top-down mechanism. Whenever you would have conflicting information from the environment, you tend to auto-complete or make sense of what you believe to be true given the facts.  There's a project that I'm working on using this BRIMS method in reinforcement learning and trying to understand how this top-down attention mechanism, for instance, changes over the course of training.

> **[22:56] Generalization:**
“Instead of trying to accomplish that (out-of-distribution generalization) directly, we’re trying to accomplish modularity through an inductive bias first and then achieve out-of-distribution generalization.”

> **[37:38] The importance of deep work for researchers:**
“Having a mechanism that keeps you focused on a single goal or a single target is absolutely crucial I think.  Recently I implemented a strategy where I put my phone away for a month, and I could see my productivity just increasing. I calculated it. It was roughly tenfold.”

<br>

### Show Notes

* Giancarlo on the relevancy screening mechanism in his paper, which resembles human memory consolidation [00:00]
* Intro [01:00]
* Giancarlo’s path from pure math to travel, startups, data analysis and machine learning [02:15]
* What drew Giancarlo to Yoshua’s lab? [05:03]
* Combining pure math/dynamical systems and deep learning [05:31]
* Giancarlo’s recent NeurIPS paper on mitigating gradient vanishing [08:43]
* Memory consolidation as an analogy for their screening mechanism [09:36]
* RIMS/BRIMS and SCOFF [13:51]
* Why is out-of-distribution learning & generalization critical to the field? [16:01]
* Bottom-up and top-down mechanisms in the brain and BRIMS [20:47]
* Using inductive biases and modularity as an approach towards out-of-distribution learning [22:46]
* Inductive biases through competition [24:29]
* For more inductive biases: Anirudh Goyal’s paper, “Inductive Biases for Deep Learning of Higher-Level Cognition” [27:41]
* Most promising approaches to compositionality [29:35]
* Giancarlo’s fascination with the human brain, subconscious, and causal inference of the mind [30:15]
* “Hopfield Networks is All You Need” and extensions [31:24]
* The importance of mathematical foundations for deep learning [32:13]
* Giancarlo’s work on a new transformer architecture [33:38]
* Managing deep work hours as a researcher [37:15]
* Giancarlo’s 2019 NeurIPS paper [46:11]
* Research lessons learned along the way (e.g. learning the review process, start with simple problems and toy tasks, reverse engineering tasks for testing) [50:12]
* Benchmarks and tasks for out-of-domain generalization [52:34]
* Metrics for success in research [53:21]
* Giancarlo’s other interests: psychology, the subconscious mind, mental health [54:39]
* Using neural nets as inspiration for psychology [55:25]
* Discussing explanatory models for psychology and mental health issues [56:14]
* Mila’s research culture, collaboration and productivity [1:05:04]

<br>
*The transcript is coming soon. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*

