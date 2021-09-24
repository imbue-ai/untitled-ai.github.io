---
layout: post
title:  "Generally Intelligent #14: Yash Sharma, MPI-IS, on generalizability, causality, and disentanglement"
date:   2021-09-24 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://www.linkedin.com/in/ekitanidis/">Ellie Kitanidis </a>
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-14-Yash-Sharma--MPI-IS--on-generalizability--causality--and-disentanglement-e17rdev" width="100%" frameborder="0" scrolling="no"></iframe>

<br>

Yash Sharma [(Google Scholar)](https://scholar.google.com/citations?hl=en&user=AlGCn8wAAAAJ&view_op=list_works&sortby=pubdate) [(Website)](https://www.yash-sharma.com/) is a Ph.D. student at the International Max Planck Research School for Intelligent Systems. He previously studied electrical engineering at Cooper Union and has spent time at Borealis AI and IBM Research. Yash's early work was on adversarial examples and his current research interests span a variety of topics in representation disentanglement. In this episode, we discuss robustness to adversarial examples, causality vs. correlation in data, and how to make deep learning models generalize better.

Below are a few highlights from our conversation as well as links to the projects and people referenced in the episode.

<!--more-->

<br>

## Some highlights from our conversation:

- "The way we train neural nets, the way we do supervised learning, it's super convenient, and it's gotten us very far. But the way we do it is so different from how humans learn. Neural nets are trained from scratch on IID images and one-hot labels. Humans learn on interactive, dynamic experience where their task is constantly changing and they're always observing distribution shifts."

- "It's difficult to think how academics can really contribute when they aren't able to train at that kind of compute scale like Google or Facebook can. But if we study formal problems, where the problems can be studied at small scale, we can make progress."

- "The disentanglement definition, kind of what was put out by beta-VAE, was saying 'we want each dimension to represent different information.' But [...] some things literally can't be put into a single continuous latent. If I talk about 3D rotation, 3D rotation is correlated. So how am I going to put three-dimensional rotation into a single latent dimension?"



<br>

## Referenced in this podcast:

- Key papers that inspired Yash's interest in adversarial examples: [Szegedi et al. 2014](https://arxiv.org/abs/1312.6199), [Goodfellow et al. 2014](https://arxiv.org/abs/1406.2661), and [Carlini & Wagner 2016](https://arxiv.org/abs/1608.04644)
- [Matthias Bethge's lab](http://bethgelab.org/), where Yash is doing his PhD work
- [Bernhard Schölkopf](https://www.is.mpg.de/~bs) and his work on [causality](https://arxiv.org/abs/1911.10500)
- [The Book of Why](https://www.amazon.com/Book-Why-Science-Cause-Effect/dp/046509760X) by Judea Pearl
- Foundational work on disentangled systems by [Irina Higgins](https://scholar.google.com/citations?user=YWVuCKUAAAAJ&hl=en) and coauthors: [beta-VAE](https://openreview.net/forum?id=Sy2fzU9gl) and a [more recent paper from 2018](https://arxiv.org/pdf/1812.02230.pdf) working towards a definition of disentangled representations
- [Yoshua Bengio](https://yoshuabengio.org/) and his work on "factors of variation"
- [Locatello et al. 2018](https://arxiv.org/abs/1811.12359), which won best paper at ICML 2019
- [Invariant Risk Minimization](https://arxiv.org/abs/1907.02893) (IRM) by Arjovsky et. al. and a follow-up paper [In Search of Lost Domain Generalization](https://arxiv.org/abs/2007.01434) by Gulrajani & Lopez-Paz
- [A recent paper on non-linear IRM](https://arxiv.org/abs/2102.12353) by Lu et al.
- [AI-generating algorithms (AI-GAs)](https://arxiv.org/abs/1905.10985) by Jeff Clune

<br>

## Further discussions:

- Yash brought up the dilemma of exploration vs. exploitation in research, explaining why he decided to switch his focus in grad school instead of continuing to build on his expertise in adversarial robustness. In particular, he noted that incoming grad students in an increasingly competitive admissions landscape are often expected to already have experience in whatever topic they plan to specialize in. **How can new researchers optimally balance exploitation of previous experience with exploration of the broader field?**

- We discussed how lack of robustness to adversarial examples provides a human-to-AI comparison that seems worth digging into, as it demonstrates severe out of distribution generalizability. On the other hand, these are not naturally occurring distribution shifts. **Beyond its practical security implications, does robustness to adversarial examples have anything to teach us about intelligence?**


<br>
<br>

*Thanks to <a href="https://www.linkedin.com/in/tessajhall/">Tessa Hall</a> for editing the podcast.*