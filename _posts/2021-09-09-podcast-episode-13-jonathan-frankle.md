---
layout: post
title:  "Generally Intelligent #13: Jonathan Frankle, MIT, on the lottery ticket hypothesis and the science of deep learning "
date:   2021-06-17 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-13-Jonathan-Frankle--MIT--on-the-lottery-ticket-hypothesis-and-the-science-of-deep-learning-e175j3j" width="100%" frameborder="0" scrolling="no"></iframe>

<br>

Jonathan Frankle [(Google Scholar)](https://scholar.google.com/citations?user=MlLJapIAAAAJ&hl=en) [(Website)](http://www.jfrankle.com/) is finishing his PhD at MIT, advised by Michael Carbin.  His main research interest is using experimental methods to understand the behavior of neural networks. His current work focuses on finding sparse, trainable networks.

Jonathan's 2019 [paper](https://openreview.net/forum?id=rJl-b3RcF7) on the lottery ticket hypothesis, which won best paper at ICLR, shows that neural network pruning can reduce the parameter counts of trained networks by over 90% while preserving accuracy.  This is done by retroactively pruning and naturally uncovering subnetworks with winning "lottery tickets," meaning those whose initializations make them capable of training effectively.

He is currently on the faculty job market, and is also looking to help conferences implement new reviewal processes. Some of his ideas include metadata cover sheets to guide readers, and different categories of ML papers with distinct and appropriate criteria for selection (science vs. engineering vs. artifacts). Please feel free to reach out to him!

**Highlights from our conversation:**

🕸  "Why is sparsity everywhere? This isn't an accident."

🤖  "If I gave you 500 GPUs, could you actually keep those GPUs busy?"

📊  "In general, I think we have a crisis of science in ML."

<br>
*Below are some highlights and the show notes. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
<!--more-->
<br />

### Some Quotes We Loved
> **[42:37] The kind of research Jonathan prefers to work on in ML:**
"So I tend to be a big advocate for doing this more scientific style of research where I ask a question, design an experiment, and make sure that the question you ask has a good answer either way. You can write a paper if the answer is "yes" and you can write a paper where the answer is "no." And everybody will like it either way. It's hard to come by those questions, but I think it's easier to come by a question like that than it is to get an engineering technique to work in a space where you don't know whether it's even possible."
>
> **[1:01:49] Building software engineering principles for ML:**
"My advisor, Michael Carbon, is a programming language researcher, and he sees the world through that point of view. And he keeps referring me to the phenomenon of what's called 'code collapse.' You can look at the Wikipedia article. This was sometime in the seventies when essentially we only had assembly and we only had these relatively low level languages and we didn't know how to build large scale software yet.
>
> Systems just fell over frequently. Systems would just collapse because we didn't know how to make sense out of giant software systems built in this way. We needed new principles and new research on this discipline called software engineering...That's how it feels right now.  We don't necessarily know the right principles at the right abstractions. And it's much harder because we're not controlling ones and zeros. We're controlling this weird animal we don't understand that learns in a way we don't understand. But, the same principles may apply. And this should give us some hope that we can get to a better place with these kinds of systems. We can make these into real engineering tools."


### Show Notes
* Jonathan's background: CS at Princeton, adjunct professor at a law school, then grad school at MIT [3:52] 
* Working on police use of facial recognition in 2015 [6:35]
* The reason Jonathan went back to grad school [7:58]
* Being at the intersection of tech and policy [8:25]
* Jonathan's first grad school focus: security and privacy [10:49]
* How Jonathan came across the idea for pruning and his eureka moment [11:00]
* Developing the lottery ticket hypothesis, from XOR tests to M-Nest [11:55] 
* Dealing with lack of resources as a beginning grad student [17:01]  
* Describing the lottery ticket hypothesis paper and network pruning [19:35]
* Linear mode connectivity [paper](https://arxiv.org/abs/1912.05671) [24:55]
* Crisis of scientific rigor in machine learning research [30:02]
* The current most important questions in Jonathan's field [31:00]
* The relationship between hardware and software for accelerating progress in the use of sparse networks [34:38]
* Challenges during the paper writing process and approval for developing the lottery ticket hypothesis [36:35]
* Using more of a scientific methodology in ML vs engineering (creation vs. question answering) [42:37]
* Simultaneous discoveries and the adjacent possible [44:30]
* Methods to find papers that describe the science of deep learning - basic experiments which get at how neural networks work [45:00]
* Why the current state of ML research doesn't make sense and ways to improve upon it [47:24]
* What work of Jonathan's has been overlooked? [53:10]
* Collecting and analyzing data on facial recognition systems from a hundred police departments [58:05]
* Jonathan's controversial research views [1:00:25]
* Jonathan's mistakes as a researcher and what he learned from them [1:05:50]
* Jonathan's batch norm [paper](https://arxiv.org/abs/2003.00152) [1:11:10]
* Low-level tips to make more progress as a researcher (solid software engineering skills) [01:15:30]


*Thanks to <a href="https://twitter.com/lukelivesfree">Luke Cheng </a> for writing drafts of this post and <a href="https://www.linkedin.com/in/tessajhall/">Tessa Hall</a> for editing the podcast.*