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

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-08-Giancarlo-Kerg--Mila--on-approaching-deep-learning-from-mathematical-foundations-etk3ep" width="100%" frameborder="0" scrolling="no"></iframe>

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

*Below is the full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*

<!--more-->

<br>
**Giancarlo Kerg:**
Humans, the obvious sparse attention, we can remember things from childhood. How are we able to do so? How are we able to do credit assignment of extremely long timescales? So we must have sparse attention into the past or something like that. We found a way to basically use those theorems and develop a screening mechanism where we basically go from a quadratic computational complexity of self-attention into linear computational complexity, where we consider a fixed time horizon, where we compute some type of relevancy score for a given state and then we decide by a simple heuristic whether we should keep this state and memory or not. But over a very fixed time horizon. In hindsight, it actually resembles the process of memory consolidation, which is the transfer of memory tokens from short-term to long-term memory, and then the short time where we computed this relevancy score is actually analogy to the short-term memory basically. And then the long memory is what we store to thing in. It gives us a little bit like an intuitive analogy to what the brain is doing.

**Kanjun Qiu:**
Hey, everyone, I'm Kanjun Qiu, and this is Josh Albrecht. We run Untitled AI, an independent research lab that's investigating the fundamentals of learning across both humans and machines in order to create more general machine intelligence. And this is Generally Intelligent, a series of conversations with deep learning researchers about their behind the scenes ideas, opinions, and intuitions that they normally wouldn't have the space to share in a typical paper or talk. We made this podcast for other researchers. We hope this ultimately becomes a sort of global colloquium where we can get inspiration from each other and where guest speakers are available to everyone, not just people inside their own lab.

**Kanjun Qiu:**
Giancarlo Kerg: is a PhD student under Yoshua Bengio, and Guillaume Lajoie at Mila. And he did his master's at the University of Cambridge in pure mathematics. He works on out of distribution generalization, modularity, and compositionality and memory augmented neural networks, which are all topics we'll be covering in this conversation. Welcome Giancarlo, it's really good to have you. So we always start with tell us, how did you develop your initial research interests and how have those evolved over time?

**Giancarlo Kerg:**
I come from a mathematics, well, as a teenager already, I did the math Olympiads and that was my passion. The choice to study math was quite natural. It was an extension of that. I was always a problem solver. As I went into my master's, I realized that pure math is very hermetic in some sense, that people that do pure math, often times, I feel they have a little bit of an Ivory Tower taste. I was looking around to find something that is more applied and the more in touch with the real world, and that was back in 2012, roughly. So actually the two masters in pure math after figuring out that I didn't want to do pure math anymore for a while, I was just, I'm not sure what I should do.

**Giancarlo Kerg:**
Well, first I traveled around the world for six months and then I worked in a bunch of startups and in marketing and then slowly but surely I gravitated towards data analysis, data science, and then eventually machine learning. And that was around the time when machine learning became really popular, 2013, 14. I knew back then that this is going to be the future because of the increasing demands on the job market. And so I pivoted and I aligned myself with eventually deep learning and all this. I initially was doing some research projects in statistical learning theory. In Berlin, I was doing that at the university for a few months, and then after that, I applied for internships in the US and so I started as a doing deep learning for cancer immunotherapy.

**Giancarlo Kerg:**
I started my PhD in Montreal with Yoshua Bengio in 2017. I just had no clue what exactly I wanted to do. I just felt from my industry experience that it was absolutely crucial to have some practical deep learning experience, because I felt like that was the major bottleneck to my productivity in industry, and also just solving machine learning problems in general. I felt like there was a lot of these cooking recipes and little tricks that one has to know, and if you don't know them, you can just spend a lot of time just exploring a bunch of stuff. I felt like that was the right thing to do to just go back to academia and do a PhD in deep learning and to learn all the tricks of the trade basically.

**Giancarlo Kerg:**
Eventually, I also started to understand that I might not necessarily be so interested in the super practical stuff, but rather sort of understand deep learning from a more principled point of view. I eventually gravitated towards dynamical systems and understanding how can I basically combine my mathematical knowledge from before into deep learning and have a more slightly rigorous understanding of what is going on? That was the starting point from where it all developing into what I'm doing right now, which I'm looking at memory augmented neural networks, I look at how while gradients propagating in recurrent neural networks, and in self attentive neural networks, which is the paper that I published. Recently, I was also very interested in out of distribution generalization, modularity, compositionality, and these things, absolutely crucial to the field of deep learning. I'm working really hard on the next paper, which just missed the deadline for ICML, but hopefully I'm going to make it for NeurIPS.

**Kanjun Qiu:**
One thing I'm curious about is what do you tell Yoshua's lab in the first place?

**Giancarlo Kerg:**
I was in New York City at this lab doing cancer research. I basically thought I would stay there for some reason. They were doing some changes and they basically told me that I would have to reapply somewhere else. And I was considering to go back to academia actually anyway. So since they had a really good connection to Mila or Yoshua Bengio, and that they just encouraged me to reapply there. They've already an ongoing project. And then I got accepted.

**Kanjun Qiu:**
And you said you started out being interested in dynamical systems.

**Giancarlo Kerg:**
Basically I'm being supervised by Guillaume Lajoie, who's a neuroscientist and dynamical systems guy also in Montreal. In Canada you usually have four to five years, but the first year course is a little bit like in the US but less long. So you have these courses. And so initially I did just did all these courses. And then I looked around and there was Guillaume who also taught this class on dynamical systems and that's how I got interested in it. Because Guillaume is a connection between the math that I know or the thing that I'm doing right now, which is deep learning.

**Giancarlo Kerg:**
I felt like the field was lacking a little bit more of a mathematical understanding. A lot of people are just running a lot of random experiments and there's a lot of hyper parameter tuning and sometimes you just don't really have a feeling of what is going on, you just try blindly what works. And there's also these inflation of papers. Sometimes I feel like a lack of structural understanding to certain things, it definitely needs more rigor in some aspects and also the culture of mathematics, sometimes people who are thinking of mathematics as almost useless, we need the rigor, we need math in deep learning. It's just very hard to apply sometimes because you don't really know what the gradient is doing, but making an effort to incorporate mathematics, I think it will have great benefits to deep learning.

**Josh Albrecht:**
Your most recent paper is a pretty good evidence towards that, right? And that isn't super amazingly sophisticated or impossible. I mean, it points to like a really good idea basically.

**Giancarlo Kerg:**
It allowed an application of mathematics to deploy because sometimes it's not actually super straightforward how to apply it in deep learning, because this uncertainty that you have, you don't know where the gradient is going, which basically just calculating the gradient in great depth and then just proving that in some cases you can say some things about the gradient and I figured out these terms.

**Josh Albrecht:**
Is that actually the origin behind this most recent paper, or was coming at it from just proving random stuff about the gradient and then?

**Giancarlo Kerg:**
Paper was Yoshua's idea. He had this idea of proving that we mitigate gradient vanishing in self attentive recurrent neural networks. And so he just asked me, "Can you prove it?" I've had a few attempts at the prove, and then eventually I got it. There were some minor things initially that I was not so sure about it, but eventually I think I got it. And eventually we were just looking for practical application of it. I mean, it's just supposed to provide a guarantee of something that I think was common knowledge, that if you have self attention that you would somehow mitigate gradient vanishing. But I think a clear rigorous understanding of maybe all the edge cases, and when does it break down, and how can we specify self attention? And to what extent and how so that the grading propagation is still beneficial?

**Giancarlo Kerg:**
From there we thought about, okay, how can we illustrate this with some practical algorithms? How can we make use of this? Because it's not like a paper where you have a state of the art results as in the new methods, but it's the other way around, constructed the theory first for whole family of methods, and then we gave an example of a method where we prove that we have the desired properties and we can now scale for really long sequences. But it's not supposed to be a super fancy state of the art. I think it turned out to give some really good results, actually in some tasks.

**Josh Albrecht:**
Sure, people who are listening, who might not have read the paper, the title is Untangling Trade-offs Between Recurrence and Self Attention In Neural Networks. Do you want to give it maybe a few sentence description or overview of what the main idea is, and the main takeaway, and some of the parts of the paper, just so that people are on the same page as the rest of us who have read it?

**Giancarlo Kerg:**
Recurrently neural networks, they suffer from the gradient vanishing problem. What I prove in the paper is that if you have a self attentive recurrent neural network either you would mitigate gradient vanishing, and then since you have a computational bottleneck of OT square quadratic computational bottleneck, whenever you use self attention, the question is on the one hand, you have these great gradient propagation properties, but you cannot really harness them simply you have this bottleneck of computational complexity. So you could potentially scale, but you effectively can't because you can scale to some extent, but not really long by some other cognitive science motivations and inspiration from neurosciences like... While, they also have these sparse attention, we can remember things from childhood, how are we able to do so, how are we able to do credit assignment over extremely long timescales?

**Giancarlo Kerg:**
And so we must have sparse attention into the past or something like that. How can we implement that in such a way that we have some type of computational effective way to deal with attention and at the same time also get this sparsity slash is gradient propagation? So on the one hand we have the gradient propagation properties we don't vanish, and then on the other side, we have the computational bottleneck. We wanted to have the best of both worlds, meaning we want to get rid of the computational bottleneck and we want to maintain the gradient propagation properties. We found a way to basically use those theorems, I found these upper bounds and guarantees for gradient propagation and develop a screening mechanism where we basically go from a quadratic computational complexity of self attention into linear computational complexity, where we consider a fixed time horizon, where we compute some type of relevancy score for a given state and then we decide by a simple heuristic, whether we should keep this state and memory or not, but over a very fixed time horizon.

**Giancarlo Kerg:**
So the funny thing now is that in hindsight, it actually resembles the process of memory consolidation, which is the transfer of memory tokens from short-term to long-term memory. And then the short time when, where we compute relevancy, or this relevancy score and that analogy to the short-term memory basically. And then the long memory is what we store to thing in. So it's thing to memory, that's the long-term memory, and then we use the short term memory to compute relevancy. And it gives us a little bit like an intuitive analogy to what the brain is doing, but of course this isn't the justification of anything yet.

**Kanjun Qiu:**
That's really interesting that you came up with that first and then you realize the connections to memory consolidation, I would have imagined that it happened the other way around.

**Giancarlo Kerg:**
It's a nice story to tell, but in actuality, it happened the other way around. I first proved it, then I came up with the method and then I realized that it was again, an analogy to memory consolidation.

**Josh Albrecht:**
After realizing that connection, did you go and learn more about memory consolidation or how similar is it? What are similarities and differences?

**Giancarlo Kerg:**
I read a bunch of neuroscience papers that some of them were really technical. And I have to admit, I did not understand so much, but I did understand a little bit of what's going on. And it would definitely be interesting to understand whether the brain has some type of saliency detection slash screening mechanism, what the kind of function that the brain uses to screen out events that are not relevant? One thing we know approach probably is emotional saliency sort of things that had an emotional impact to us, but I don't think this is the only solution. So probably there's other solutions, probably there's combination of multiple things most likely. One thing that I want to investigate at some point is can we actually meta learn this screen heuristic. So can we actually come up with a metal learning algorithm to this mechanism of putting something into memory? You can view this as a policy, and then can you actually meta learn this policy in some sense?

**Josh Albrecht:**
I think that was part of what was marked as future work and the paper is how exactly does this consolidation work?

**Giancarlo Kerg:**
And you mean it end to end or is there? Because it seems the way we did it, it's very much heuristic and it's very real in some sense. And very well to settings where you have a sparse set up from the get go, you just have a few characters to keep in memory and then it's just seems to work. But the real world is not necessarily a toy task. So how can we extend that idea to the real world? And it might give rise to interesting methods, but you need to find the right tweak to it.

**Josh Albrecht:**
Did you guys try this approach on other sort of non toy tasks as well, or things that didn't end up making it in the paper?

**Giancarlo Kerg:**
We're still doing it actually, but projects are taking over. And gave a lot of exciting results too. I gave priority to this other project first, but we'll definitely be interested to keep on working on this.

**Kanjun Qiu:**
How do you feel about the approach now that you develop the method and you realized it has some similarities to memory consolidation? Do you feel the general principle is fairly generalizable or do you feel there's some stuff that's brittle about it?

**Giancarlo Kerg:**
Since we were talking about a vanilla RNN plus self attention or … self attention. I feel in general, these methods, they can't necessarily generalize very well because of the lacking modularity or compositionality. That's something that the field needs more of. I think we have seen great papers like Rims and Brims and Scoff, all these papers, the basic ideas that you factorized knowledge in the specific way, you break it down into different modules or something like that and then since you have these different modules, you can recombine them flexibly so you don't mess up the whole model. But if it was something in the input distribution changes, it doesn't affect everything, it just affects maybe a tiny part of the whole structure because it's just not one single module or something like that. We're breaking knowledge into different pieces that can be flexibly recombined in changing environments.

**Kanjun Qiu:**
The pieces of the story that determined as relevant and then stored into long-term memory, quote unquote, can then be used in different circumstances.

**Giancarlo Kerg:**
Yeah. So the point was, we just have a general connectivity matrix. We don't have any modules that are competing in some way or something that forces some type of factorization, but I think the method can potentially be combined with something like that. It's basically taking the idea of how can we make sense of what's happening right now, and reason over large timescales and decide what to put into memory and what to leave out and so on and so forth. The thing is also causality happens over time. It's not you just have an MLP and then you look at the data and you try to figure out the causes. But if you have sequential data, then you already know what that causes always happens before the effect. These causal chains that I'm talking about in the paper where you have these relevant events, it might be that a subset of these paths between relevant events that might give rise to causal reasoning of some sort.

**Josh Albrecht:**
And people are saying, what were the names of the techniques? I think you mentioned Rims or Brimms or Scott or something. What was the papers that you were mentioning?

**Giancarlo Kerg:**
They are basically papers by Anirudh and collaborators. So Anirudh is a guy that also is also on my paper. The idea of Rims, and essentially also Brims is you have competing modules that are competing for explaining the data that forces some type of specialization and factorization on the knowledge, and therefore it makes it a more flexible in out of distribution setting.

**Kanjun Qiu:**
Earlier you mentioned, you're really interested in out of distribution generalization, and modularity, and compositionality, and that these are very critical to the field. That feels obvious to me, but can you explain what is it that makes these critical and what do you see that's interesting at the moment?

**Giancarlo Kerg:**
I would say probably the number one bottleneck in deep learning is that, I mean, there's a series of terms how people who call these effects, though some people say it's spurious correlations, some people say surface learning. There's this clever Hans analogy. There was this story of this German horse, people thought it was like a genius. And the master of the horse showed him a math equation and the horse was supposed to tap with the left foot whenever it was correct and with the right foot, whenever it was incorrect. And everybody was like, "Wow, this horse is a genius," right? And then later at some point, the wife of the master did the same thing. She showed the math equation and suddenly the horse was completely wrong. People were okay, "What is going on? We fought this horse would understand the mathematics," right?

**Giancarlo Kerg:**
And what was actually happening is that the master, whenever the equation was correct, was actually smiling and whenever the equation was incorrect, he was not smiling. And then it was actually picking up on whether he was smiling or not, not actually understanding mathematics. And if you want to talk about intelligence, you want to talk about something where you understand the true mechanisms behind what you just seems to correlate in this very instance. And this is the problem in deep learning that it learns the associations that are the easiest to pick up on. In the case of the horse, it's much easier to pick up on the smile rather than understanding the equations. And so that is a little bit what's also going on in deep learning, deep learning the model doesn't really know, oh, this is not supposed to be this, it's just coincidence. It learns all these correlations between things and associations between things that are actually supposed to be completely uncorrelated or that they have nothing to do with one another. They just seem to happen, they coincide statistically speaking in this setting.

**Giancarlo Kerg:**
But if you would change this, if you would go out of distribution, these two things might not be correlated anymore. The model would break down completely. And that is also why we see that, especially in business, people do not trust deep learning that all that much. They think, "Oh, no, we want to have a model that's interpretable. We can see really what's going on." What we really need is we want to have something that factorizes the knowledge in such a way that we can generalize out of distribution. And we don't have these spurse correlations are happening. You see an x-ray for instance, and you want to see whether the person has a specific disease. And it happens at all the people that have the disease have been treated before in some way, and they have this metal thing. And then you see that on the picture and then the deep learning algorithm just picks up on the metal thing.

**Giancarlo Kerg:**
You need to put some pressure on the system either by augmenting your data set in some way, but then you can just get rid of the spurious correlations that you know of and that you're aware of. But if there are already things that you don't explicitly see or explicitly know of, and then you cannot really direct and you would just have to hope that this would happen. And so another way to practice this is by using inductive biases to pressure the system to factorized knowledge in such a way that it's actually generalizable. The thing that we would need to do in the long-term is find the right inductive biases that would put pressure on the system to generalize well. We have seen this in distribution generalization, you have this very generic regularizes L2 law and L2 regularizer drop out or whatever. They are just very generic. They might work well in some instances, but for out of this distribution generalization, you need a smarter way to put pressure on the system or like better inductive biases.

**Giancarlo Kerg:**
And what inductive biases does the brain use to generalize out of distribution. It seems a lot of neurons are cooperating in some way to have this effect. It's believed somehow that this happens through competition of bits of information or neurons. Maybe they are cooperating in some way and then there's one group that competes against another group. And we also see this when we form sentences that we have a potential sentences that we have in our head, that we have an idea that we want to formulate and we have potential sentences. And then we started with one sentence and we realize mid sentence, oh no, the other formulation was better and then we started all over again. It's almost like we hold these two things at the same time in our heads. And then we just take the winner. The winner takes it all kind of thing.

**Kanjun Qiu:**
Yeah. That's really interesting. We observed this at so many different levels, at the sentence level, we also observed that sometimes you have warring feelings in your head or voices in your head, different parts of you wanting to do different things. So it does seem there's some kind of, at least multiple kind of predictions are being generated. And then there's something that's choosing between them.

**Giancarlo Kerg:**
There's these words that have multiple meanings and depending on the context of the sentence, you think almost immediately of the right meaning, given the sentence. You hold those potential other meanings also in your mind for like a split second or something like that, and then you just eradicate them from your consciousness instantly, because you already know this is the context, so this is something that is very similar in nature to the Brim's paper, which is block RIMS. And the title is not called Brims, but the method is called Brims. Rims, so rims would mean recurrent independent module, or because they are open modules we call it Rims. Brims is like block rims essentially, they have a rims, but on two layers where the sort of second layer is modulating the attention on the lower layers. Whenever it is ambiguity in the data, there is a lot of noise or there's potential multiple meanings, then there's a top-down mechanism that's firing, helping the bottom up perception to go to the right place.

**Giancarlo Kerg:**
In neuroscience we have this bottom up perception and you have the top-down is basically what you believe to be true, like the context of the prior beliefs and everything. And then when the bottom up signal is ambiguous, you auto complete it with a top-down mechanism. So whenever you've got conflicting information from the environment, you tend to auto complete or make sense of what you believe to be true or given the data. So example, the sentence is the context, and we have ambiguous the word it has multiple meanings, but you auto complete it with what you believe to be true basically. You can really see the neurons are, or the attention mechanism from top down is firing really strongly if you have an ambiguous environment, or if you have noise environment, something that you can actually see in the model itself.

**Giancarlo Kerg:**
I'm actually also really interested in continuing working on that direction as well. There's a project that I'm working on using this Brims method in reinforcement learning and trying to understand how does this top down attention mechanism, for instance, how does it change over the course of training? How does it correspond to the phases of exploration and exploitation? If it's going to be super useful, I have no idea, but it's just something.

**Kanjun Qiu:**
It's a quite an interesting formulation of this brain has both top down and bottoms up and like how to mine them together. I think a lot of people think that out of distribution generalization is an important problem, the most important problem in deep learning and tackling it from different perspectives. But you talked about modularity and compositionality. What exactly do you mean by modularity and compositionality?

**Giancarlo Kerg:**
There this idea that we want to do out of distribution generalization, instead of trying to accomplish that directly, we're trying to accomplish modularity in through an inductive bias first and then achieve out of distribution generalization. What is modularity, it's breaking down or factoring knowledge into two different pieces that can be flexibly and dynamically recombined as the input distribution is changing. Let's say you have different entities in your environment and they have dependencies and you would try to factorized the entities with their dependencies in some modules that are sort of like almost independent from one another. So if the setup is slightly changing or the circumstances are shifting, you would still be able to make sense of your environment because you have this meaningful factorization of your environment. So that is the idea of modularity, how you would achieve this out of distribution generalization. And the question is what are the right inductive biases or what is the right way to put pressure on the system to achieve that?

**Giancarlo Kerg:**
So the idea is increase, you have almost too much capacity in deep learning. And then the question is, how would you constrain that capacity? It's like in regularization, you increase the model capacity, but to layer on constraint to give good generalization, but here you have this model capacity and you try to restrict it in some meaningful ways, such that this inductive bias that you're using would put pressure on the system to the factorize and break down the knowledge into modules or factorize the knowledge in a way that it generalizes out of distribution. There's a lot of inductive biases that people are thinking about and thread that always keeps coming up is this idea of competition between several entities or modules. It seems like … in some sense or another is key to this out of distribution generalization.

**Giancarlo Kerg:**
It's almost like in the economy and because of the competition, you're forced to specialize. That is also going on with modules that are competing for access, or that are competing to explain the data. They are forced to specialize in some way and therefore just pick up a very specific part of the environment. And then another module might be almost unrelated and pick up a specific auto relationship of the environment. And then, so if just one relationship is changing just this one module would change instead of the whole thing changing.

**Kanjun Qiu:**
I wouldn't have thought about it in terms of competition before. At least I imagined competition is not the only way that you would force specialization.

**Josh Albrecht:**
True. Although competition seemed like a really great one. I think when I heard you saying some of this stuff before, a lot of the things that I see that kind of make me a little sketched out, basically are places where people were adding inductive biases of, oh, now we have a list of entities and relations. It's like, ah, I'm pretty sure we don't have that inside of our brain. It's not that explicit. And so competition is a nice idea because it's a little more generic and it doesn't require us to put these human ideas about what form of information and really explicit forms into the network.

**Giancarlo Kerg:**
There's the global workspace theory that Yoshua is really all about. And you can view your subconscious mind as a reservoir of all sorts of information and ideas, and then there's a bottleneck, and then there's all these entities that are competing. And these coalitions that are being formed between different entities that are competing for this access to conscious. Imagine you would want to infer the cause of something that happened to you. You hold all these different hypothesis in your mind, and as you keep thinking about it, I got more information. Eventually one of them is going to win. And then this would simplify your cognitive process in the sense that you wouldn't need to hold all this simultaneous and conflicting information, you can just basically go like this hypothesis wins and so I can basically make sense of the reality in this way. And then you can move forward with your model construction of reality basically.

**Giancarlo Kerg:**
The information that are making it to the bottleneck in this case, consciousness, how they get access to the entire information. Like on the one side, have a lot of capacity on the other side we have something that is restricting this capacity. And one potential avenue to do that is to enforce some type of competition. There's probably a lot of inductive biases that might help. This is one inductive bias that really fascinates me and I want to understand some more.

**Kanjun Qiu:**
It makes me wonder if the bottleneck in humans is consciousness, is the part of our mind that's able to express itself? And what is the bottleneck in animals means?

**Josh Albrecht:**
I think a lot of people don't give it quite enough credit to animals.

**Kanjun Qiu:**
Why do you things behave? Yeah, I don't know.

**Giancarlo Kerg:**
I would expect that to be the same with animals. Animals also are able to do out of distribution generalization and walk around in different environment. If you put a dog on a skateboard he would probably also be able to do some things, I don't know.

**Kanjun Qiu:**
Yeah. They just have no explicit prefrontal cortex.

**Giancarlo Kerg:**
That is definitely a big problem.

**Josh Albrecht:**
Are there other inductive biases beside the competition that are really fascinating to you or other ways of reducing this modularity?

**Giancarlo Kerg:**
But there is an interesting paper by Anirudh and Yoshua that I think it's called Inductive Biases For Higher Level Cognition. And they list all sorts of inductive biases. But I think this is the main one. And well, another one is the idea of having a sparse factor graph. You have the encoding of the entities on one side and you have the encoding of the relationship between the entities almost on the separate side. First, the relationships, there's a sparse amount of relationships that are being encoded. So there is some neuroscience evidence that I think there's also something that happens in the brain. You have to underline on the cortex that encodes these relationships. And I think the hippocampus then brings the relationships together with the sensory input. And yeah, it seems like brain is doing something similar to encode the relationship almost like. And that's also how interaction emerges I think. That you have some type of encoding of the relationship that's almost can be repurposed to many different entities.

**Giancarlo Kerg:**
You can think of the abstract idea of like a mother and an aunt or something like that, and it's just the relationship between two entities. Let's say the person accented and it's on, but it can be applied to many families, right? It's certainly not just tied to yourself and your aunt, it can be repurposed in many different setups. I think this is another thing that will definitely help with modularity, let's say out of distribution generalization radar. Compositionality is this idea that think of one piece of information as being composed of other pieces of information that are units, and there is many different ways to encode information, but compositionality is a very narrow subspace of all the ways you can encode information. And just because you could express compositionality in a model doesn't mean that you will, or you will end up bringing it. Our languages is built up this way, right? So do we need the right inductive biases to achieve that? How specifically can we implement that and achieve that?

**Kanjun Qiu:**
What do you think are the most promising approaches to conditionality?

**Giancarlo Kerg:**
Competition for sure is one way to achieve it, having this idea of recurrence or iterative learning, it's allowing information to be processed in a very effective way and to be flexible. So flexible to out of distribution, we can achieve out of distribution generalization and that we can handle changing environment because the real world is always changing. If you want to have something that is truly intelligent and that is able to flexibly adapt to environment, different environments, then we would need something that breaks down information into sub entities of some sorts that can be flexibly recombined.

**Kanjun Qiu:**
What are some work that you feel like has impacted you the most?

**Giancarlo Kerg:**
There is an invasion of papers. It's really hard to keep track of everything. In terms of what has impacted me the most, I think the recent papers of the Rims and Brims, and this idea of modularity, I think is just really fascinating. But I'm just scratching the surface and there's a lot more to be discovered. I'm just generally very fascinated by the human brain and especially the subconscious mind and how we also humans, we do causal inference in our brain, or we process our environments in a way that is flexible. All these different questions of what the brain is doing is it's just very interesting to me. I read one paper that talks about the different avenues of neuroscience research that can be interesting, or it could be applied to AI.

**Giancarlo Kerg:**
That also actually made me think of this memory consolidation aspect, understanding what is going on in the brain. Right now, we are thinking of, okay, what are individual neurons doing? Maybe what we need to ask is can we describe what a group of neurons is doing in some ways? Maybe are they interesting connections to dynamical systems theory. Hartfield wrote a recent paper, I think it was an extension on the Hop Field Is All You Need, or it was a response to that. I have to dig more into this kind of material to understand more about the connections between deep learning and dynamical systems.

**Josh Albrecht:**
There was a lot of really good stuff in there.

**Giancarlo Kerg:**
It's something that you see very rarely in machine learning that people make the effort to really write out the math and be really rigorous about everything. It's mostly a bunch of experiments and then interpretations they're off. And then they just hope that interpretations that are solid enough to make it through the new process. And that I really like those papers. He also wrote the bunch of papers of the same kinds. The other one was rudder and also wrote like 100 pages or, and then, and I don't think a lot of people are going to read it, but I think they should.

**Kanjun Qiu:**
Speaking of mathematical foundation to deep learning, it feels like it's the kind of thing that's actually necessary if we really want to, as a field understand what is going on versus just the papers.

**Giancarlo Kerg:**
It came out in August and there's a lot of people that already have build on this. And there's also a lot to unpack from this paper. So I think taking the time to really go through all the math. And I think it's also much better to understand one thing in detail rather than understanding lot of things a little bit. In terms of efficiency in research it's much better to stick to one thing and go really deep rather than trying to do a lot of the things at the same time, especially with this explosion of papers, you get easily to just read a lot of papers superficially and just keep it very vague understanding of what's going on rather than trying to pick one thing and go really deep at it.

**Josh Albrecht:**
In your next research direction that you're working on now, how are you thinking about the math and the experiment for the new research directions?

**Giancarlo Kerg:**
Actually, this project that I'm currently working on is more coding focused. For me personally, it's just a good practice because I have a math background and I was never really the guy that was always like in front of his computer coding. So I only coded when I had to, but generally I have not read the 70 pages, but I will definitely finish them at some point and try to understand really all the methods and techniques for the proofs and everything, especially because I'm working on something transformer related at the moment.

**Josh Albrecht:**
I thought it was a really cool exploration of what are transformers and why do they work? That's not how it's build. There is some potential and the memory thing shows the Hopfield network sort of way of thinking about it and transformer way of thinking about it are just use or different ways of thinking about it. You can actually use this to express a bunch of other networks as well, a bunch of other techniques as well. This is really sort of broader theory of this, which tells you this is why you picked this crazy concept that then they're in transformers for this one - some bizarre constant they having there and it's, "Why did you pick that particular way of normalizing those things?" And they kind of explain, "Oh, it's kind of border between these two behaviors and the Hopfield networks." Oh, okay. Yeah. That's the reason for these things that you happened upon empirically, but nice to know why that's there.

**Giancarlo Kerg:**
In Mathematics sometimes gives you some insights that you would not always have through just running your experiments, especially now that the transformers are making such breakthroughs everywhere. I think it's crucial to understand them. 2020 was a year of a series of mini breakthroughs with transformers. I was particularly excited about the Alpha Field 2 breakthrough.

**Kanjun Qiu:**
Why is that?

**Giancarlo Kerg:**
Yeah, I think it just has a lot of implications. It will bring the fields of deep learning and medicine/genetics closer to each other. And we usually had these kind of nets architectures that we use for processing protein sequences or DNA. And it seems transformers are making their breakthroughs everywhere in medicine or genetics. It hints towards a deeper thing, so something that might need to understand a bit better about transformers and why they work so well to really investigate because it seems for object recognition, transformers do pretty well as well. It seems like everything is transformers nowadays. So I'm pretty excited about that and see where this is going?

**Josh Albrecht:**
Do you feel there's a connection between your neuro network and transformers, and is there a sort of some way of applying this idea of selective attention and retention of previous things that might be beneficial for some sort of new, even better transformer architecture?

**Giancarlo Kerg:**
Maybe there is connections, but it's in a recurrent neural network. You apply attention in a very special way, whereas transformers, it's a little bit different. There are some analogies of course, but I try to do is rather do the opposite of trying to take what I'm doing right now and apply it back to the old idea and see if I can extend the old idea with the new idea.

**Josh Albrecht:**
Well, what do you mean the new idea?

**Giancarlo Kerg:**
The new idea is based in the new project that I'm working on since a few months or a few weeks. It's basically a different transformer architecture that also incorporates competition and things like that. It's targeted that out of distribution generalization and the ultimate idea is how can we combine this with a memory module of some sort and we enrich recurrent neural networks with this architecture in some way?

**Josh Albrecht:**
So all connection, but maybe taking the new thing and applying it to the old one, rather than the other direction around?

**Giancarlo Kerg:**
It's really fascinating because there's a few other papers that came out of our lab the same time now. They're also incorporating more or less the same idea. So it seems to be a timely topic that everybody's so excited about it and it's making such a quick progress. I think it's there, there is this, I don't know who said this, but I think it was whenever there's a pandemic or something where people have nothing else to do, then there is scientific breakthroughs happening and....

**Kanjun Qiu:**
A pandemic, a war.

**Giancarlo Kerg:**
At least there is some positives.

**Kanjun Qiu:**
I have a theory that people talk about how great scientists are great in their '20s and maybe their brain declines or something and they don't do any great work over time. I think it's just really about focus, have a lot of focus. And so the pandemic and things that I give people a lot of focus.

**Giancarlo Kerg:**
So this is also something that is super relevant if you're a researcher or if you want to do deep work, is to manage your focus because you can easily get distracted by so many things. I mean, social media, it's such an attention grabbing mechanism and it's highly addictive and damaging as well. You also have all these papers that pop out everywhere, and you can just get distracted with that as well. So having a mechanism that keeps you focused on a single goal or a single target is absolutely crucial I think. Recently I implemented a strategy where I put my phone away for the month, then I could see my productivity just increasing. I calculated it, it was roughly tenfold. I kept track of the number of productive hours during the day. It all started with this moment when I started tracking my productive hours during the day, I was like shocked that I was only two hours or three hours productive during the day. And I was like, "This is not good."

**Giancarlo Kerg:**
We spent so much time on our phone and then it's not only the total amount of time you spend on your phone, but it's also the constant interruption. So even if you being interrupted for like a few moments, you need time to get back into the deep focus state. Actually, it was pretty hard for me because I had these dopamine responses and these cravings to my messenger or whatever, and it wasn't there anymore. I almost felt like a drug addict of some sort. After I passed the 72 hours, then I think it was fine. I want to keep that nice momentum going now that I know I kept track of the number of focused hours. It's really incredible. And not only do I work more, but I also feel less anxiety and stress in general. Instead of just having these 10 different side projects, collaborations here, collaborations there, and doing here a meeting, there a meeting, because I really wanted to make the ICML deadline, it was really forcing me to just have a single target and I could really see how beneficial that was to consider all my entire approach.

**Giancarlo Kerg:**
So having a single target, just working on the single project, because your mind is immersed. You get thoughts about your project, even when you're not working, you're walking around somewhere, you're taking a coffee, you constantly, with your subconscious mind, you're constantly on it, you go back home, you implement it and then you see what the result is. Reconvene with the group. And if you're constantly scattered, you have a little project here, a little project there, it's always you always need time to get back into it, and by the time that you're back into it, you're already out of it because you need to go to the next project. It's not just that the productivity is divided by the number of projects, but it's actually much more than that.

**Kanjun Qiu:**
I have a theory that 100 years from now, when I look back and be a context switching was way more expensive than we thought it was. And that the optimal type of work week is not, you work five days and you have two days of weekend, but instead it's, you work 120 hours a week for two weeks at a time, and then you take a whole week off and then you repeat it.

**Josh Albrecht:**
I used to like that.

**Kanjun Qiu:**
One of our mutual friends did an experiment where he did programming for 120 hours for a week. And it was like being high. It was just so exhilarating. So many new ideas, so productive got a month and a half worth of work done, basically.

**Josh Albrecht:**
Yeah. Yeah. I totally believe that.

**Giancarlo Kerg:**
If you're in a deep state of focus, time is not passing in the same way. It feels even in the minute or two, like you can really accomplish a lot in an hour of focused work.

**Kanjun Qiu:**
It makes me wonder, what is the analog in your neural nets? One day, we're going to experience some kind of interesting phenomenon in neural nets where attention switching is more expensive than not attention switching. Why? That's so interesting.

**Giancarlo Kerg:**
There is even some neuroscience experiments for visual attention. It was something along the lines of you cannot specialize your attention and at the same time shift your attention. You cannot move your visual attention at the same time, where you try to go deeper onto something. It seems there's different parts of the brain that are being activated or something along those lines. I definitely took a lot of inspiration from Cal Newport. One strategy could be that you have periods of intense focus, and then you have periods of distraction or whatever, but it's important to not be too scattered and not be having multiple times per day where you check your phone and all this things.

**Kanjun Qiu:**
There's no way that they're multitasking effectively. We were recording two to three hours of productive time of day. What did he go to?

**Giancarlo Kerg:**
Quantitatively, I don't think it's tenfold per day, but I think in terms of hours, I think it's more along the lines of six or seven hours. But it's maybe not super duper productive six or seven hours, but more maybe four hours super productive and then the other hours is maybe a little bit less productive.

**Kanjun Qiu:**
It's consistent across every researcher I've talked to. Matt, super productive focus time per day is four hours.

**Giancarlo Kerg:**
Yeah, exactly. It definitely makes sense to have a deep work session somewhere in your day. When I get off, the first thing in the morning is four hours of uninterrupted work., and the rest of the day I can have meetings and things like that.

**Kanjun Qiu:**
That's exactly our schedule.

**Josh Albrecht:**
We're pretty believers in the deep work book. One of our teammates is in your book.

**Kanjun Qiu:**
Yeah, our teammate, Jason Benn is in the deep work book as an example.

**Giancarlo Kerg:**
What is his name, Jason Benn?

**Kanjun Qiu:**
Jason Benn, B-E-N-N.

**Giancarlo Kerg:**
It seems focus becomes more and more of an asset because all the social media, you can see that less and less people are able to just maintain that focus over an extended period of time. And so all of the things that you can accomplish only by having focus over extended period of time will become more and more of a rare thing and therefore become more valuable. And therefore, if you are able to pull this off, then you will be having almost like a disproportionate advantage.

**Josh Albrecht:**
And we really care about deep work. My schedule is the same as yours, wake up, do deep work for six or seven hours. All my meetings everything's always in the afternoon. So to the lager deep work thing we put all of our podcasts on just one day. So that way it'd be, okay, we'll just do all bunch of podcasts in one day, low context switching, right?

**Kanjun Qiu:**
Everything can be maximized for low context switching.

**Giancarlo Kerg:**
Yep. Absolutely. Between focus and switching between tasks always comes at a cost and you want to do it as little as possible there.

**Kanjun Qiu:**
Well, one thing you mentioned earlier is another thing that I've heard from a lot of researchers, which is read a few papers very deeply. And one of my friends, he was one of the founders of quantum computing, the field of quantum computing when he wanted to understand deep learning as a field, his first thing was to go and try to select a set of papers that he felt were very foundational and then spend 100 hours on each paper. And so something I was wondering is you mentioned you don't read a lot of papers very broadly, you read a few papers very deeply, very focused on the areas that you're interested in. Are there any papers that you spent the 100 hours on that you haven't talked about yet?

**Giancarlo Kerg:**
100 hours is a lot. And its proves there that it takes time and really on the stack complexity and the whole making a complex prove, bringing it to the point where it's really natural. There was a bunch of papers for my master teasers that are at 10 times or something like that. That is definitely very satisfying because you get a better and better understanding. And there's something in the field of deep learning that makes me really anxious, it's this constant publishing. Paper is new thing and you get this fear of missing out, FOMO, which is sitting down and saying, "No, I'm just going to focus on this one thing," because you always feel like, Oh, maybe this becomes redundant after I read this paper or something that.

**Giancarlo Kerg:**
I heard as many researchers say the same thing that they just picked one aspect or one topic and they really went really deep. It resulted in immediately three or four papers as a result to that. As opposed to you become unattached to like publishing a lot and you go really deep on one thing and you really don't care if you publish a lot. And then ironically end up publishing a lot. After NeurIPS deadline, after summer break, I was essentially trying to go in too many directions at the same time. Initially I felt well, I'm going to publish like five papers by the end of the year. And then at the end of the day, I publish nothing. I think I just learned my lesson now and pick this one thing and just go all in.

**Kanjun Qiu:**
I have a very visual model of what research is some dimensional space with a boundary at the edge. And the boundary is human knowledge where we are, what humanity knows. And so if go really broad, you're kind of exploring and moving in many different directions within the boundary. But if you go really deep, you're going straight at the edge and then very quickly you will hit the edge and then you'll add something to it.

**Josh Albrecht:**
It makes a spike and it goes out the side.

**Kanjun Qiu:**
My internal explanatory model for why going deep produces lots of papers because you hit the edge really quickly and then you start pushing the edge outwards.

**Giancarlo Kerg:**
Yep. And then it just compounds because you have all this deep understanding that few people have and it just repeated over and over again. You can also see this with mathematicians, initially when you look at their track record of papers, oftentimes in the very beginning, they just publish around the very same thing, slight variations, look at it in this way, look at it in this way, and then after they got used to the process of research, more and more, they went a little bit more broad. And you see also the same thing in business that you pick a point, the starting point and you go really deep and then eventually you build, the flower grows and then after a certain height, it goes into the broad basically.

**Josh Albrecht:**
And you had another paper, the Catastrophic Fisher, and I was wondering if you wanted me to talk a little bit about that and the story behind that or how you were involved in that with basic idea or any of that?

**Giancarlo Kerg:**
I collaborated, but I basically just helped with some mathematical proofs and some ideas. But there's another paper that I published as a first author at Europe's 2019 that I can talk about, which I find it quite interesting. It's nothing groundbreaking. It's essentially an extension of orthogonal recurrent neural networks. It's not super interesting at this point in time anymore because we know that gradient vanishing can be mitigated with self attention. And initially it's motivation was okay, can we actually restrict the spectrum of the connectivity matrix in the recurrent neural network in such a way that it mitigates the gradient vanishing and it can learn long-term dependencies, perform well on copy task, adding task, and all these long-term independency tasks. And the idea was initially that people try to constrict the spectrum, and then there were people saying, "Oh, wait a minute, you're constricting the spectrum, but you're not spanning the entire sparse of matrices that have spectrum, and again, spectrum of one." Of all the complex numbers of modulars one.

**Giancarlo Kerg:**
There was a series of papers that were spanning this space more and more, and until eventually I think it was this ICML paper by this Oxford PhD students that uses Lee algebras and lead groups. Instead of directly optimizing on the lead group, you just view the Lee algebra as a tangent space. The algebra is the tangent space at identity of the lead group and then you do the optimization in the vector space, in the Lee algebra as opposed to the lead group. But then there was also some papers that were talking about whether you can extend even beyond unitary matrices or our matrices with eigenvectors, eigen values, some modulus one, the natural question is how can we extend beyond unitary matrices? And there were also some papers there. And the idea that I had was using a shorty composition. So shorty composition is a tool that allows you to split up the matrix into a diagonal matrix that gives you access to the spectrum and then a sort of a trianglar matrix that is keeping track of the interactions between the different eigen modes.

**Giancarlo Kerg:**
All what we've seen so far, unitary matrices are normal matrices. So therefore the second part of the matrix is zero and we can basically keep everything as is, but just enrich this whole matrix space with these triangular matrices on top, and then harness this shorty composition in order to make the matrix space more expressive. And then I said that we can learn these trends in dynamics, or be able to have these complex computations over a short time horizons incorporated in those recurrent neural networks that are able to learn long-term dependencies. I think it was an issue for some of the tasks, so PTB or water tasks where you need to do a complex short term computations, if you would just look at unitary matrices, it would be not so easy to do that because all what those unitary agencies are doing is just keeping things in memory and, but not compressing information in any way or not doing any computations that are super comparable.  It's something that I found very exciting.

**Josh Albrecht:**
Is there any future work that you obviously done that?

**Giancarlo Kerg:**
It was my first, first author paper. So it just got me some momentum and I think it was something cool to think about for a little while, but then I think it's just outdated. I mean, there's transformers for one, and then there's also a self attention that allows these long-term dependencies to be learned more actively. We can compress and learn things in a very effective way, but at the same time also have meaningful gradients. It's also from a neuroscience perspective or a cognitive perspective. It also makes more sense to think about it like that.

**Kanjun Qiu:**
To your point earlier about reading papers that become outdated in this field.

**Josh Albrecht:**
It's amazing how fast it happens, right? That was only what? A year or two ago. It wasn't that long ago, right?

**Giancarlo Kerg:**
Yeah. Yeah. I think I stretched it already. In 2019, I think it was outdated they a little bit. I was reviewing a bunch of papers for Europe's 2020, and it was a lot of people still trying to do papers in this direction and it easily gets outdated in a year or two by just other methods.

**Josh Albrecht:**
Are there any lessons you feel you've learned from either that paper or the most recent Europe's paper?

**Giancarlo Kerg:**
So the way I did research in the beginning was just, I had no clue of what the review process looks like. So getting accustomed to all of this and making sure that your paper actually fits on eight pages and getting the right kinds of experiments and things like that, and also starting with the right experiments. Because imagine you have inductive bias that you want to build into, or that we want to highlight in your work, one good strategy is to start with very simple toy tasks and work on one toy task and then another toy task, as opposed to trying to immediately get it to work on a more complex task, because you might spend a lot of time and then you figure out after a really long time, you might figure out why it doesn't work. And then you might've just given up by then.

**Giancarlo Kerg:**
Or it reminds me of these math, we'll get problems from back in the days when I was in high school, let's say you want to prove something for all N. And then sometimes N is a million or 1000 or something like that, and it's very hard to see the structure. It's very hard to grasp the essence of what is really going on in these large cases, or on these complex cases. Let's say these small non-trivial cases, once you get it working there, then you suddenly see some nugget or some idea or some structure, and then you can start to extrapolate this to more complex tasks. So I think having a set of really good toy tasks, especially for things like out of distribution generalization nowadays is very crucial. If you want to incorporate an inductive bias on that end, it might be good to have some really, really simple tasks.

**Giancarlo Kerg:**
It might be also good to some type of reverse engineering, say that you want your model to do certain things. And then you purposefully construct a task where you already know what the answer is and then you make sure that the model actually recovers that. If you want to learn the relationship between different entities, you might do this Polish calculator or something like that, where you have this plus and the multiplication. There's all these different ways where you start with super simple cases and then reverse engineering, as opposed to having a very complex, I don't know, reinforcement problem that you're trying to get state of the art right away and you just spend a lot of time building on the wrong foundation.

**Kanjun Qiu:**
The Math Olympian analogy is a great analogy. And it is this idea of start with simple problems, something actually we've heard from a lot of researchers in the podcast series. Everyone discovers it for themselves.

**Giancarlo Kerg:**
For me, I think it was rather late that I discovered it, better late than never.

**Josh Albrecht:**
You mentioned, out of domain work and generalization, do you feel there are good problems or tests or simple tasks or good benchmarks in that realm already?

**Giancarlo Kerg:**
Yeah. There have been a series of papers that came out that presented a bunch of tasks. I think there was a paper by, coming from Stanford. They had like some OD benchmarks and also inside Mila we have people that work on this quite a lot and we kind of forward to each other some toy tasks that are useful. And so I'm currently building on those. So I'm building on those, but it definitely like the field is in need for a good series of tasks for sure.

**Josh Albrecht:**
Are there any other things that you think would be really useful for the field or places where you think, oh, I wish that I could change X about the field?

**Giancarlo Kerg:**
It seems like the ultimate metric for measuring success in the field is, oh, how many papers did you have, and things like that. This automatically forces you to go into this like rat race of constantly trying to publish something as opposed to taking the time and going really deep. It's very tempting, especially if you're in a lab that is very productive. There's a lot of collaborations and potential papers that you can be collaborating on that it's very tempting to just say yes and no later than you will realize that you're you just spread yourself too thinly, and then you don't actually accomplish so much.

**Kanjun Qiu:**
I'm excited to see what comes out of it.

**Josh Albrecht:**
Me too. I love that strategy I think we might adopt something very similar to that as well. And I would love to see more people adopt that. I think the Hopfield network paper, right. I want one 10th, the number of papers and all of them to be bad quality.

**Kanjun Qiu:**
Yes.

**Giancarlo Kerg:**
What is also great about papers like these is that it's a joint effort of a lot of folks, but if you have this mindset of, oh yeah, I'm the first author. I don't want to share my research with too many people. I go on my current projects, there's five students and I think four profs or something like that. Who cares in the end, whether people are going to think, "Oh yeah, who did this work? Because this is too many students on the paper and whatever." Did you publish something that you're proud of or did you do something that make them advance or not?

**Josh Albrecht:**
That seems like a much better metric.

**Kanjun Qiu:**
Is there anything else that you wanted to talk about that we haven't covered?

**Giancarlo Kerg:**
Generally, I'm also very interested in psychology and the subconscious minds. Beside the applications to genetics and health, in general, I think mental health is something that I'm really interested in because it seems to be such a fuzzy domain where it's not really clear, what's helping and what's not helping. And there's a bit of research, but then again, there's so many people are having a depression or anxiety or whatever, and then they go to some psychiatry's and then they get some pills or did they just spend a lot of money on the therapist. Maybe AI is able to with some centralized data or something like that, and maybe eventually we'll be able to systematize this more, or make this more effective.

**Kanjun Qiu:**
I've been developing a bunch of models for psychology using neuronets as inspiration. And the interesting thing about the field of psychology, psychiatry is that it's basically impossible to examine the physical substrate. In most fields, you can understand at least the physical behaviors that are going on molecular level, but in psychology, you can't do that for depression. The interesting thing about neuronets is that we do have this kind of physical substrate that we can work with, these architectures and that they maybe are able to give us better models for depression and anxiety.

**Giancarlo Kerg:**
Oh, interesting. Interesting. In society, this is almost an open problem or something like that. And the same way you have those connections in mathematics and the open problems in AI. This is also an open problem.

**Kanjun Qiu:**
Yes. I have a theory right now that a lot of the issues with this field, we only have symptoms. We don't have any explanatory models for why things are happening. And we can only address the symptoms, but I've done a bunch of therapy. And so now the question is how do we turn them into a much more rigorous, almost mathematically rigorous models for why they cause all of these symptoms?

**Giancarlo Kerg:**
It seems there's this sparse set of causes that drive mental health. It's a very tiny subset of all the potential, just contracting it with positive thinking and all this. Did it ever really sustainably work? From the limited knowledge that I have I feel like it's a mix between environmental factors, beliefs, and unresolved emotions. You can almost describe that as a state and then given the state, what do you do?

**Kanjun Qiu:**
My current model is that actually unresolved emotions come from beliefs. Some of the beliefs you don't understand or hardly access very well, but that those basically like beliefs are like these mini neuronets in our brains with a lot of them. And they're producing all of these predictions, and some of predictions are really negative. And so as a result we have this emotion of fear that appears, this is a really negative prediction. And other times, they produce normal predictions, fine predictions. And when we're young, we form a lot of these beliefs.

**Giancarlo Kerg:**
Yeah. Default assumptions about the world that we having that might not actually be true. And then oftentimes become self-fulfilling prophecy.

**Kanjun Qiu:**
That's right. Why are they self-fulfilling prophecies? It's because if you have a belief and it makes a prediction and it predicts failure, then you will not take action because it predicts failure. And they're kind of an obvious chain of why narratives are self-fulfilling. A lot of trauma comes from childhood and seems young child's brain trauma is almost over-fitting to a particular situation. You have one thing that impacts you. And it was not even that big of a deal, but somehow you interpreted this crazy belief system out of it. And when you grow older, it seems to happen a little bit less. Children have some kind of weird over-fitting response and then a lot of those kinds of over-fit responses get carried into adulthood.

**Kanjun Qiu:**
And then one methodology in therapy that works very well actually is pulling up those childhood beliefs and showing them more data. So showing them what's happening in your life right now. And so I almost think of this as, oh, what you want to do is pull up your childhood models that have formed and give them more data in order to allow it to generalize. And so then it's not so over-fit, and it can make better predictions.

**Giancarlo Kerg:**
I was reading this book on memory reconsolidation, and if you have some trauma from the past to actually relive the emotion in some way, think your way out of the thing. Because it seems there's some stuff stored in the emotional brain and the limbic brain, or you build like a wall around it or some sort, because you don't want to feel it on a constant basis because it just messes with your productivity and your well-functioning in the day-to-day basis. So you first need to understand where it's actually sitting, because a lot of the times, the biggest bottleneck to healing is that a lot of these emotional issues slash beliefs are unconscious. The thing that controls you the most is the thing that you don't know you don't like. Once it comes into your awareness, you're halfway there basically.

**Giancarlo Kerg:**
Ultimately we want to optimize for happiness, right? We want to optimize for your human experience. And I think the most causal elements for that human experience is precisely those trapped emotions and beliefs. And once you're to think it through, it's a fundamental thing. And maybe it's because we'll are not aware of it, or they're not conscious enough of it. I don't know.

**Josh Albrecht:**
To your point earlier, we can do experiments in animal models, although animal models don't exactly transfer, but there was a really good oral or I'm sorry, spotlight, no invited talk at NeurIPS last year, one of the main presentations was about this guy about mouse depression basically. And they very much confirming what you guys are saying, it's as little infants and the little baby mice, they were like subject to a lot of stress, whether they took the mouse after this stress and put it back with it's mother or put it somewhere else, it developed depression not much later in his life when it was again, subject to stress.

**Kanjun Qiu:**
Our mechanisms for experimentation are difficult. And I think the best think to do right now is develop a theory and then I'm very much in the middle of this right now, but two experimental approaches. One is, maybe you can actually learn some things from deep neural networks, but another one is to use the existing psychological experimental tools that people self-report and something like that.

**Giancarlo Kerg:**
No, absolutely. And I think another avenue would be that you just take yourself as an experiment, work on yourself because you have the most data about yourself.

**Kanjun Qiu:**
All of my explanatory models are from me doing a ton of therapy on myself and understanding, oh, actually, and changing your beliefs and rewriting your narratives completely determines your outlook on life. Rewriting my old emotional responses and understanding where they came from and helping them generalize better. They completely changed...

**Giancarlo Kerg:**
There was this one guy that had really severe social anxiety, and it seems you have a really rough childhood. And he stumbled upon this one book called Homecoming by John Bradshaw. And he just did his inner child work, getting rid of the childhood trauma and everything. And it was super painful. And he had to almost disappear for three months and we did all the exercises in there. And when he came back, he was almost like a newborn person. I was, "Wow, this is crazy transformation that you just did." Some people would really crazy breakthrough with this and other people it almost didn't do anything. And it seems you're given the blueprints, given the sets of beliefs, given the set of emotional trauma slash schemata or whatever, how you call it, you need to do breath work, you need to do hypnotherapy, journaling, or inner child work, and then this is your way out. If you had a recommender system that's on your phone or something that gathers all, that would be absolutely amazing.

**Josh Albrecht:**
There are different techniques that will work really amazingly well for certain people. Instead of danger with using your own self as an experimentation tool is back to the exact same problem over-fitting, it works really well for me and it might even work really well for other people that are very similar to you, but you probably do need this big suite of tools. And there might be other really good ones that are out there too. But if people could just get access to the top 10 or something, that probably would be pretty great.

**Giancarlo Kerg:**
Yeah.

**Kanjun Qiu:**
I don't know. Not that I disagree with you need a lot of tools, having a lot of tools is good, but there is an explanatory model for why certain tools work on certain people and other tools don't. That model is what's important to understand it.

**Giancarlo Kerg:**
Looking at this book by John Bradshaw and a bunch of other psychology books, what I saw oftentimes is they have, is like a bunch of quizzes in the beginning of the book to allocate you to the right chapter. They give you a sentence and then you have to score, oh, it's rather true or rather not true. Or this is false, or this is true. And if you had like a database of handpicked question, that internal representation, and depending on what you've clicked, let's say you have a quiz that's dynamically adjusting to you and you would get a series of statements and you just click yes or no, and then depending on what you've clicked on in the past, you would get a statement that would be the most informative about your internal state.

**Giancarlo Kerg:**
Within maybe 100 statements, you will get a very precise profile of what this person's set of beliefs is, where he's stuck emotionally, and then maybe use that as a descriptive state of what this person's starting point is. And then that might be a way to encode it because I don't see otherwise how you would gather this information, right?

**Josh Albrecht:**
That's an interesting idea.

**Kanjun Qiu:**
That's really interesting. That's a encouraging idea.

**Giancarlo Kerg:**
I was thinking about doing something like that, but then I was like, ah, I got to publish, I got to publish.

**Kanjun Qiu:**
Which fields?

**Josh Albrecht:**
And then you just telling us you don't need to publish yet.

**Kanjun Qiu:**
I guess you're in the middle of your PhD. There's something very important here. If my life's work is to figure out how to enable people to be happier, it seems like there's something very worthwhile.

**Giancarlo Kerg:**
That's a good way to think about it. I mean, I enjoy math, I enjoy coding and things like that. But this is in terms of meaning, the meaning component is not always there in a very super theoretical work. It's pulling on an intellectual level, but it's not necessarily on the human level, mostly in machine learning or AI it's you probably some stuff and then it stays in the journals and then you move on to the next thing. And maybe it's fun, but having that meaningful impact on where you really directly see. I even was thinking about, I should study psychology from scratch and I was like, "Ah, I'm like 31 now. And going back to school." There might just be a way to combine both things without having to study everything from scratch.

**Kanjun Qiu:**
I don't think you need to study psychology from scratch. I feel I've gotten really far without doing that.

**Giancarlo Kerg:**
And she also, because a lot of the knowledge you get at university oftentimes is not the most practical knowledge, right? When I look at the most useful tools that I develop on myself, I'm thinking hypnotherapy, I'm thinking breath work, do you really learn this at university? I don't think so.

**Kanjun Qiu:**
Exactly. This is the much more practical stuff that will give you a much better sense of the actual causal factors.

**Giancarlo Kerg:**
And they ought to do experiments on those things. And I think that because it's not scientifically validated in this traditional sense and why we don't really know whether this works, is it's just Hocus Pocus? But then at the end of the day, people that are experienced with this kind of knowledge, they know what works. I'm not trying to listen to someone who has solved their own problems then some researcher that does a theoretical work on psychology.

**Josh Albrecht:**
Have you ever been part of a research group or lab that you felt was particularly effective? One of the things you mentioned is that Emulate that you guys have internal toy problems that you were sending back and forth. And that struck me as well, interesting example, maybe that's part of what helps some people at Mila be so productive and so effective. Are there other things that you've seen or have you ever been part of a group that you thought was really effective?

**Giancarlo Kerg:**
So I think that the most effective research environment I've been part of is definitely Mila. Maybe I've given the wrong impression that Mila is highly organized, where we all had to have a list of toy experiments that we send around. I mean, it's just almost by coincidence that I know about it is because I know this one person. It's a lot of different groups that are almost independent from one another, that some people that are very social, they know a lot of other people, they get involved in a lot of projects, they know a lot of things, and some people maybe then they don't go to other people so easily to talk to them. And so they might be more isolated and doing things on their own. So it's a giant lab and information doesn't necessarily always flow everywhere in this same way. It gives you a lot of freedom to lower, you're not always under pressure to publish and perform, but at the same time, it puts just about the right amount of pressure.

**Giancarlo Kerg:**
It's almost like regularization. It's like you have these specific things that you need to accomplish in your PhD, you have these quarters, you have these presentations, many teasers that you need to do before, I think the end of the second year, and then you need to publish, I think three papers or something like that. Or at least that's a sufficient condition to graduate. There's a lot of bright minds. You have a lot of professors with different knowledge. You have people from all walks of life, neuroscience people, computer science professors, that have all sorts of different backgrounds, mathematicians, you have postdocs coming from physics. It's a very sort of a rich environment where you can just easily collaborate. And it's just effortless. I would assume that in smaller research labs, it might not be so easy to be always on the up-to-date on the latest trends, because I feel the lab is so big that we have reading groups for every single topic out there, subfield. There is a reading group just doing neuro AI. There's a reading group just doing that meta learning, there's a reading group just doing deep learning theory.

**Giancarlo Kerg:**
And so whenever you want to know about something specific, you just go to the social group and then you just connect with a bunch of people and you get someone on board that can help you out. And it's also in terms of pre Corona, we moved out of the university, we merged with the McGill Lab. It's very close in proximity to other industry element AI. I think Facebook research is also in the building. It's like an open space. You don't necessarily have any separate rooms except for professors. And everybody just walks around and you have this gigantic kitchen in the middle that people talk to each other. And we also see that people are very interested in topics that are not only touching AI, but also economics. We even have a group on mental health, on Asian and yoga. It's just an exchange of ideas. And that makes it very effective, I think.

**Kanjun Qiu:**
How do yu get pulled into a collaboration?

**Giancarlo Kerg:**
I never really thought about it. It always came natural to me and people ask me, "Oh, how do you find the people to collaborate with all the time?" Okay. So I think one strategy that I use is when I see an interesting paper that comes out of Mila, then I will see who is the first author, and then write I'll write to this person on Slack just to have a chat or something like that. Because if I see that it might be an idea that you can combine with something that I've done or it touches on some of my interests, I'll just reach out and we have an informal chat and if we have a good vibe going, then we can keep chatting and then eventually something happens or nothing.

**Giancarlo Kerg:**
There's a danger of having too many different projects and too many collaborators. Then we have this adverse effect of having being too scattered. And that also definitely happened to me. It's like saying yes to everything and then also not wanting to let anybody down and things like that. Having a lot of collaborations is not always necessarily positive. You also need to focus. It's finding that right balance. I'm really happy that we found a really nice group that has very complimentary skills on the project that I'm working right now. It has a really good momentum and I'm really happy about it.

**Josh Albrecht:**
Great. That's a really good conversation. I've learned a lot. I took a bunch of notes, a bunch of cool ideas as we were talking. So thanks so much for going through everything.

**Giancarlo Kerg:**
Yeah, well thanks for having me and I hope I could offer some info and interesting insights.

**Kanjun Qiu:**
Thank you for listening to Generally Intelligent. We love feedback and questions. So please feel free to ping us on Twitter at @Kanjun and @JohnAlbrecht, or email us with any ideas or questions. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes, and follow us on Spotify, or your favorite podcast app. Thanks very much and we'll see you next time.

