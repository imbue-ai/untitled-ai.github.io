---
layout: post
title:  "Generally Intelligent #9: Drew Linsley, Brown, on inductive biases for vision and generalization"
date:   2021-04-01 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-9-Drew-Linsley--Brown--on-inductive-biases-for-vision-and-generalization-eu2cm2" width="100%" frameborder="0" scrolling="no"></iframe>

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

*Below is the full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*

*Thanks to <a href="https://twitter.com/lukelivesfree">Luke Cheng </a> for writing drafts of this post and <a href="https://www.linkedin.com/in/tessajhall/">Tessa Hall</a> for editing the podcast.*

<!--more-->

<br>

**Drew Linsley:**
And so, over the past five years, I think we've put together a pretty interesting theory through several papers on how understanding the brain and circuits in the brain specifically can help us build better artificial intelligence. And so the crux of this theory is that the biases in vision represent heuristics essentially, or shortcuts taken by the brain, which are shaped by the statistics of the visual world, of our visual surroundings.

**Drew Linsley:**
And so, when you imbue an artificial model of vision with such shortcuts, what you get as a biproduct is a whole host of really interesting phenomenon. One, strictly for the machine learning audience, what you get is what's known as sample efficient learning. Two, you can have better generalization, to low level noise that may be added to images, then a model without a search biases. And then third, you get this ability to generalize, to what's commonly known in the field of computer vision, artificial intelligence, as domain shifts. So you can generalize two examples which are completely novel in a sense to the training set.

**Kanjun Qiu:**
Hey, everyone. I'm Kanjun Qiu, and this is Josh Albrecht. We run untitled AI, an independent research lab, that's investigating the fundamentals of learning across both humans and machines in order to create more general machine intelligence. And this is Generally Intelligent, a series of conversations with deep learning researchers about their behind the scenes, ideas, opinions, and intuitions that they normally wouldn't have the space to share in a typical paper or talk.

**Kanjun Qiu:**
We made this podcast for other researchers. We hope this ultimately becomes a global colloquium where we can get inspiration from each other and where guest speakers are available to everyone, not just people inside their own lab.

**Kanjun Qiu:**
Drew Linsley, is a postdoc in computational neuroscience at Brown, where he's advised by Thomas Serra. He builds computational models of the visual system that can help us both explain biological vision and also solve challenges faced by artificial vision. If you enjoy this episode, Drew is hosting a workshop at ICLR called, Generalization Beyond The Training Distribution In Brains And Machines where there'll be contrasting inductive biases versus a dual approach. You can find more information for the workshop on our blog post for this podcast.

**Kanjun Qiu:**
Thanks for joining us. I guess the first question that we always start with is, when you first got into the field, what were your research interests like? Why did you enter the field and how have those evolved over time?

**Drew Linsley:**
So, I think I have a somewhat unorthodox entrance into the field. My background, I did a PhD in cognitive neuroscience, so I was studying mechanisms, very broadly stated mechanisms, in the brain that might support our ability to recognize where we are in the world. For instance, recognizing objects or spatial properties of our scenes and how those might give rise to more complex forms of perception.

**Drew Linsley:**
And my PhD started in 2011, and, as I'm sure you two know, and probably all the listeners know, 2012 was a big year for the field because of the ImageNet competition. So, I saw this happen, I saw a model that was very loosely inspired by a hierarchical organization of visual processing areas in visual cortex, how such a model was able to just blow the field away in terms of recognizing objects in natural images.

**Drew Linsley:**
So, here I am, studying vision, studying the neuroscience of vision, and I see a model of something that you can write down and really, no longer do you have to talk to people and experiment on people, you have this model that you can now interrogate, potentially we could use this, or I could use this, to generate theory for how the visual system works, how vision works, but then also an existential question that I hope neuroscientists deal with is, why are we studying neuroscience?

**Drew Linsley:**
So you could be in the field to try and develop treatments for dysfunction in the brain. You could be in the field because you're so fascinated by questions of how the brain works.

**Drew Linsley:**
These kinds of open questions of nature just are enough to drive you in your research. I liked those perspectives to neuroscience, but for me, the concept that research I'm doing in the lab could inform artificial intelligence, which to me has such broader implications, you're going to be able to impact not just neuroscience, but to develop tools and theory for understanding the brain, but also medicine, also robotics, physics, every scientific field is being influenced by our developments in artificial intelligence.

**Drew Linsley:**
So, it's almost like the greatest ROI on your research is in this field. So if I could offer anything, and with my background in neuroscience, to machine learning, then I was really fascinated by that.

**Drew Linsley:**
So, from there, I applied for a MIT summer school, which is called the Center for Brains, Minds and Machines and this is a fantastic summer school organized by Tommy Poggio at MIT, amongst others. Gabriel at Harvard, of course, I'm taking courses at BC where I was at the time, but when I immersed myself in this summer school, I was able to meet the leaders of the field and see that their interests, maybe not their backgrounds, but their interest didn't diverge so far from mine. So that gave me a model for how I could develop as a researcher.

**Drew Linsley:**
And then the next big step I took was once I finished my PhD, I was able to work with Thomas Serre at Brown University. And so when I was looking for post-docs, I was looking for a specific thing, which is somebody who is interested in neuroscience, like myself, but then also a leader in computer vision and artificial intelligence, which I was not.

**Drew Linsley:**
So, unfortunately Thomas, took a chance on me and so over the past five years, I think we put together a pretty interesting theory through several papers on how understanding the brain and circuits in the brain, specifically, can help us build better artificial intelligence.

**Drew Linsley:**
And so, the crux of this theory is that the biases in vision, what we look at are contextual effects, broadly defined, which I'll explain in a second, but these biases, in vision, represent heuristics, essentially, or shortcuts taken by the brain, which are shaped by the statistics of the visual world, of our visual surroundings.

**Drew Linsley:**
And so, when you imbue an artificial, the model of vision with such shortcuts, what you get as a biproduct is a whole host of really interesting phenomenon emerge. So one, strictly for the machine learning audience, what you get is what's known as sample efficient learning. So, what that means is if you give your model fewer samples to learn a task, it's going to reach a criteria and performance in fewer samples than a normal model, more efficient learning of a visual task.

**Drew Linsley:**
Two, you can have better generalization, and we can talk about this question, generalization, more further, because that's a very expansive topic, but better generalization to low level noise that may be added to images, then a model without a such biases. And then third, what you get, and this is largely an implementation detail, all of these things are closely linked, the way we implement these biases is through, what I call, recurrent models.

**Drew Linsley:**
And so, this is a way of reusing, reapplying weights over and over again to an input. And so the way you can think about this is essentially, almost like, dynamic program or some wild loop where you can apply a sub-program to a problem over and over again until you've sufficiently processed the input.

**Drew Linsley:**
So what's cool about that, is essentially you get this ability to generalize, to what's commonly known in the field of computer vision artificial intelligence, as domain shifts. So you can generalize two examples, which are completely novel in a sense to the training set. Now it's only novel in a sense, because these new examples are composed of the same visual features that were in the training set but in a new configuration, a novel configuration.

**Drew Linsley:**
So now, bringing this all back to the brain, what I believe is that by understanding how the brain works, and the understanding I think needs to be at two levels, first, by building computational theory, which you can say at a cognitive level of how we process sensory inputs, how we learn from those inputs, and how we learn and convert those inputs into memory. And then, how we form decisions based off of our inputs, all these different cognitive level descriptions of intelligence are central to developing theory for what is the desired way of learning and developing intelligence systems.

**Drew Linsley:**
But then, two, I think if you work at the level of circuits, and so what this means is at the level of inhibitory and excitatory cells and how those connect together and shape processing inputs. If you link those two levels of analysis together, then I think what you can get is some interesting biases, which aligned with biological intelligence and as a result, you're essentially building inductive biases into your artificial intelligence systems.

**Drew Linsley:**
So inductive bias, just describes any shortcut that you're taking or any bias that you're adding to your system, which will help it learn the data distribution that you're applying to. Now, the reason why I think it's important to look to the brain, going back to this question, is because there's no way that an engineer would sit down and think that it's good to have an illusion in the system.

**Drew Linsley:**
And so, that's exactly what we found in our research. Let me explain what this means. If you've taken psychology 101, if you've seen the dress on the internet, if you've looked at a duck bunny, do any of these examples ring a bell?

**Kanjun Qiu:**
The dress one.

**Drew Linsley:**
The dress. The colored dress. Okay. So I invite you and everyone to look it up. It's a dress where depending on biases in the visual system, you may see it as appearing whitish and bluish, or yellowish and goldfish. This is just from memory. This is a little bit different because it's unclear if that kind of bias would be important for artificial intelligence systems. It's an open question. Maybe jumping ahead a little bit, that's an open research question that others can pursue.

**Drew Linsley:**
So this is a contextual illusion where the explanation is that, your perception of the color of the light is going to influence how you perceive the color of the dress. Are you looking at it right now, Kanjun?

**Kanjun Qiu:**
I'm looking at it right now and I see-

**Drew Linsley:**
What color do you think it is?

**Kanjun Qiu:**
I see a yellow and white dress.

**Drew Linsley:**
Okay. How about Josh?

**Josh Albrecht:**
Well, she's looking at Google image thing, which very clearly shows the different ways of viewing this.

**Kanjun Qiu:**
No, no, no. Here's the... I'm giving him the Wikipedia. So some people see blue?

**Josh Albrecht:**
I can see why you are saying blue.

**Drew Linsley:**
I know I saw something different than my wife did there.

**Kanjun Qiu:**
Wow.

**Drew Linsley:**
So, the kinds of illusion of biases that we have worked on in the past are similar to that. Just much more artificial. Okay. So there's things called the orientation-tilt illusion.

**Kanjun Qiu:**
That's fine. This isn't one of your papers.

**Drew Linsley:**
So that's really interesting because essentially depending on the context, just to describe this illusion, what it is, is you have gradings, and you have a center grading, and then a surrounds grading, and those may be aligned or not. And what's interesting is you're asked to judge the orientation at the center grading, depending on the surround orientation, your perception of the center will be pushed to the right or to the left.

**Drew Linsley:**
So what does that tell you? Not just that your perception of the world is different than the vertical properties of the world, so that perception is not the ground truth, but also that there's an interesting nonlinearity. Almost like an XR.

**Kanjun Qiu:**
Oh, interesting.

**Drew Linsley:**
I mean, why would we have all these biases, and it's not just in this low level visual example or the dress, and by the way, we would call those two different domains, vision. So, one is orientation, the other is color, and there's different neural systems governing perception for both of those. So there's nothing to say that the same circuits are going to underlie both of those biases.

**Drew Linsley:**
You start to look into biological intelligence and you see these all over the place in working memory decision-making. And so, that's a big part of neuroscience is just to document things, but neuroscience is largely descriptive too. And so that's where the fun part comes into play.

**Drew Linsley:**
And this is more, I think of myself as computational neuroscience, try to build a mechanistic model of those phenomena, which can tell you how to generate them, essentially, based off of whatever input is coming into the system or the mechanisms that give rise to those, and more importantly, are those mechanisms functional or are they epiphenomenal, because you have all these biases, but not all of them are going to be important, probably.

**Kanjun Qiu:**
There are so many interesting things here. So just to summarize, you started in neuroscience and you got really interested in computational neuroscience and the intersection of neuroscience machine learning and where you are at the moment is how can we build models that accidentally produce some of the weird visual illusions or effects that we experience? The models are a mechanism that can explain our visual system because we can't go in and dissect it and actually examine the true physical substrate. And so the model is a replacement for the physical substrate.

**Drew Linsley:**
It's funny you say that because, we are all trying to do that. In general, you're right. It goes back to this broader question of what is the right way forward. I think the biggest "breakthroughs" in AI over the past several years have been from companies like OpenAI, which adopts a distinctly different viewpoint towards research than I do. I've been told this, I've never interviewed at Google, but I've been told when you interview there, the question they ask you is, "Okay, you're working on an interesting research problem, what would you do with our resources?"

**Drew Linsley:**
And so, what they expected you to answer is with infinite scale, what can you accomplish? That is the hypothesis that I think companies like OpenAI are testing, and it's a valid. It's good that they're testing it, and the proof is in the pudding. GPT-3 is unbelievable as are their new vision models, but this goes back to statistical learning theory that there's a fantastic paper by Stu Gemen from Brown University and colleagues, I think LGB been in stock, and this is in the 1990s. It's not necessarily brand new then, but he summarizes the problem succinctly. And this is called a bias variance trade off.

**Drew Linsley:**
And so, if you take machine learning, you'll know about this. IS means that you're going to force a model towards a certain type of hypothesis. To learn a certain set of solutions, I'd say. Okay. Now in the absence of any knowledge of ways of right bias to add to your model, you can just pump it full of data. And so, that is what companies do, right now for image classification. I think the datasets are up to, I don't know, 300 million exemplars for language. I'm not even sure how big those datasets are. It's like the whole of the internet and the models are breaking a trillion parameters.

**Kanjun Qiu:**
Yes.

**Drew Linsley:**
Okay. So now, what can that do? If you're banking on that strategy, what you're implicitly saying is, "We want to turn this problem of generalization into one of interpolation." Now let's think about generalization for a second. There's many different kinds. Generalization is talked about as a well post problem. You're sampling exemplars from the population for training and using the same sampling procedure, you're grabbing another set for testing.

**Drew Linsley:**
If you can do that with images or with self-driving, then you're in the clear. If you can successfully sample from the distribution of natural images, then this is a good strategy to adopt. Now, alternatively, we can look at the existence proof or intelligence, which is biology. And so, we don't only have to look at humans, mind you, we can look at mice, we can look at flies. Neuroscience is very difficult so it might even be better to look at what we're forms of intelligence, but point being that these animals, they can perform intelligent behavior that is beyond the pale of what we can do now with any of these low or no-bias artificial intelligence models.

**Kanjun Qiu:**
That's right.

**Drew Linsley:**
Yeah. The question is, do you want to spend all of your resources pursuing this huge data, no-bias model approach? Or, do you want to, maybe, identify some of the important biases adopted by intelligence systems for navigation and decision-making vision, et cetera, et cetera, and hope that those will help you in artificial intelligence? One more point, the biproduct of that, of looking to biology and embedding those concepts into your artificial intelligence systems, so that you can also contribute to neuroscience.

**Drew Linsley:**
You can start to screen for these various mechanisms and their importance in intelligence can do.

**Kanjun Qiu:**
Yeah. We're totally with you here.

**Josh Albrecht:**
Mm-hmm (affirmative). I think of them actually, as complimentaries. The brain has tons of parameters, tons of neurons, it's very powerful. We are going to need to scale things up a bit. We're going to want things that can generalize a little better.

**Kanjun Qiu:**
But you want to scale it the right thing.

**Josh Albrecht:**
Yeah.

**Drew Linsley:**
Which's interesting because this theory of scalability, it's entirely shaped by the hardware that we use. It's possible that the hardware we're using, and I know others have put forth this criticism. The hardware we're using is just a bad fit for some of the biological biases that might really break the field open. In that way, they're doing the right thing, punch it as far as you can, and then develop hardware further and then develop software.

**Josh Albrecht:**
Progress on both sides is actually really useful though, because as people find other software approaches that get really good performance, but, like the hardware isn't really there for them, it helps also incentivize creation in hardware. I have some friends that are working on other crazy types of hardware for, "How would you make? "How would you know?" But not in the same kind of hardware. And that could be dramatically lower power or more efficient in lots of different ways. It's just, you need different algorithms and different hardware so exploring both of those axes.

**Kanjun Qiu:**
Going back to earlier on how it's important to figure out what the biases are, so that you end up actually scaling some of that doesn't have to be infinitely large and can be a lot more simple, efficient, what are your thoughts on the important biases? Maybe there are so many, and we don't really know what they are. How do you, in your work, pick what to explore?

**Josh Albrecht:**
And, maybe, using a specific example of paper.

**Drew Linsley:**
Okay. So let me tell you a broad thesis here. Even taking a step back from this notion biases, my advisor, Thomas Serre, worked with his advisor, Tommy Poggio, on a model called the each-max. Each-max is a really important model. There was the initial hierarchical network model and then Tommy and Maxwell Riesenhuber used this model to generate hypothesis about how hierarchical processing works in the brain, specifically that there's something called max-pooling, which is followed by sub sampling. And when you have max-pooling, you build up invariants, followed by selectively, which you build up through filtering.

**Drew Linsley:**
And so, now you have two steps that you can build up a visual system, you filter, then you build up selectivity with Culling that you filter and so on and so forth. And what was really nice about that, is it explained super interesting empirical data, neural recordings from inferior high-level visual cortex in monkeys.

**Drew Linsley:**
You can find neurons are completely invariant to these paperclip objects. So objects without any semantic information, but these paperclips shown at different scales, so you have complete scale and variance on neurons, and then also at different positions, this develops some theoretical understanding of why you would want such an operation, and that this operation is also implemented in brains.

**Drew Linsley:**
This is called HMAX, and this describes a specific processing in the visual system. This goes back to psychology 101, but you're talking about what's called pre-attentive processing versus attentive processing. Pre-attentive processing is something that's probably influencing your vision right now, contrast. And you can tell that I am not just like a texture part of the background, and you're looking at me against the windows, in front of the podcast audience. I know podcasts, aren't a visual medium. So I'm seeing in front of my windows, that I am not on with the windows because of the saliency amongst other cues of my color with my background.

**Drew Linsley:**
And so, this is Pre-attentive vision. But we also know that this pre-attentive vision is only a small part of the visual perceptual experience. There's attentive vision, which has been associated with feedback processing. So pre-attentive vision has been associated with feedforward processing, which is all by the HMAX, attentive vision, which is one of the functions that describes is our ability to attend throughout our visual scenes. This is associated with feedback processing in the visual system.

**Drew Linsley:**
How do you possibly build a feedback model? There's much less known about feedback in neuroscience than there is about feedforward processing. But what you know is that feedback is a major driver of some of those biases that I mentioned, such as the orientation-tilt illusion.

**Kanjun Qiu:**
Dumb question. How do we know that feedback is a cause of the illusion.

**Drew Linsley:**
Right. I know, it's a really good question. So this gets a little nitty gritty into the neuroscience and what you have in the visual system are receptive fields of individual neurons. And so when you stick a probe into the brain and you're going to flash some stimulus in front of the observer, yeah. It's not going to be a human.  If I’m the animal, and you're going to move that stimulus and rotate it, what-have-you, until the neuron that you're recording from activates, until it starts responding to that stimulus.

**Drew Linsley:**
So you can lengthen or shorten the stimulus and you'll find the perfect size of that stimulus to elicit a response from the neurons. And so, that field is called the receptive field. This is known since people on visual who are the Seminole neuroscientists visual neuroscientists. Now, once you move that stimulus slightly outside the receptive field, you're going to get no response, but it show a stimulus in the receptive field and the separate stimulus right outside the receptive field, what you get is a nonlinear response and nonlinear interaction between the two.

**Drew Linsley:**
And so, right outside the receptive field is what's known as the extra classical receptive fields. The thing is that this nonlinearity doesn't happen immediately. So you may have an immediate response in the classical receptive field, which is evidence of a feedforward drive to that classical receptive fields. But if you look at the time course, and we're talking about like milliseconds, right? You will have a gradual change over the course in the milliseconds when you introduce the stimulus to the extra classical receptive field.

**Drew Linsley:**
So now, you look at delusions, you have similar studies for the time courses in these illusions, there's recurrent mechanisms involved in how these illusions come about, but now you have evidence from the brain on the bias. And so what we want to do is we want to build a functional model of feedforward processing.

**Drew Linsley:**
We started where we could. So we started with these biases. We built up a model of them combining of these descriptive models from neuroscience into one, which we could train with gradient descent and optimize for arbitrary tasks. Our first interesting finding was that if you begin with this feedback model of biases and you fit it to contour stimuli and optimize that model for contour stimuli, and you look at what that model is doing to solve the task, well, it's learning something that's similar to what's called in cognitive science, perceptual grouping. Gestalt based perceptual grouping.

**Drew Linsley:**
And to elaborate on that, let me first tell you about this dataset, which I think is becoming more and more relevant. So this is a dataset which we call Pathfinder. There's two long contours, where one of those either has two dots on either end or both of those have one dot on either end.

**Drew Linsley:**
So your task is to tell whether a long contour has a dot on either end. Now, what makes it slightly harder is the contours are embedded in displays of small distractors, smaller contours. We can generate these on the fly super fast, and what we found at the time was it's a little bit harder to train deep neural networks like resonates, it's a lot harder to train those, to solve that task then is our bias based model, which we called a model of horizontal connections, which is just like a way that feedback is implemented in the brain.

**Drew Linsley:**
What's more interesting, though, is first, this same dataset, there's a paper at ICLR this year, the same dataset is now being used as a benchmark for transformers. When we tested CNNs and our model on this dataset, we used images that were, forgetting now, but let's just say 150 square pixels.

**Drew Linsley:**
They found that transformers can only solve the task to the 70% accuracy when they're trained on 16 square pixel or 32 square pixel versions of the task. But when you scale up to 150 or 160 square pixels, transformers can't solve the task. So there's a couple of papers at ICLR that are using this task this year, it seems to be outstanding challenge for transformers.

**Josh Albrecht:**
These are transformers that are looking at this and taking the image as a sequence of pixels?

**Drew Linsley:**
Right. So it's supposed to learn how to connect the long contour within a vector of pixels. The longest that these contours can be is about 14 paddles long. So just draw that in your mind, 14 paddles long within 150 square pixel image. It's not that long, but what we find with our feedback models...

**Kanjun Qiu:**
What the paddle?

**Drew Linsley:**
Right. So, just imagine a long contour, but it's made up of discrete units, paddles. Sorry. I'm assuming that, dash line exactly, 14 dashes. Our model, the way it learns to solve the task is to find the dots and then to incrementally group the dashes from one dot until the end of the line. If it reaches another dot, then it has a positive example, if it doesn't, then it's a negative example. In cognitive science is known as transitively. So it's a specific class of operation.

**Drew Linsley:**
Again, going back to dynamic programming. It's about incrementally building up a solution. What I find so fascinating about that Knoll result for transformers is that despite having access to the full image, this is an operation that it can't successfully learn to do. Let's just say it's struggles to learn to do. And now probably with enough hyper parameter tuning, certainly with enough data, somebody will figure out how to solve it. But I think these relative weaknesses of different classes in models are really instructive.

**Drew Linsley:**
So, especially, if we want to move beyond transformers, which we will eventually, it's good to take what they do well, which is looking at the entire scene at once, if you're talking about images, and then associating individual parts of that scene, grouping those together. But to group a long set of objects together, the components of the lines and Pathfinder, that seems to be something that these models struggled to do.

**Kanjun Qiu:**
Hmm. I was wondering what was your theory of how to choose next and explore inductive biases.

**Drew Linsley:**
All right. Thank you.

**Josh Albrecht:**
You were talking about yours specifically, but before about the horizontal connections and talk on the feedback.

**Drew Linsley:**
So, now we have this model of feedback and we want to understand if the biases might give rise to some functional benefits. And so, we found that it did. But this is a model that was applied to these synthetic Pathfinder images, so making a positive statement about feedback or these biases helping vision was very limited at that point.

**Drew Linsley:**
So, our next step was to extend that into a model for not just feedback via horizontal connections, which is what we did for that Pathfinder paper, but also another kind of connection, which is called top-down feedback. Let me explain that a little bit. So imagine that you have a feedforward model, a CNN, and let's say this is roughly a model of the visual system. Then each layer in the CNN represents a layer in visual cortex. Horizontal connections, describe connections between units within a layer. That is important, potentially, because you can do interesting normalizations.

**Drew Linsley:**
You can subtract out a global illuminance, you can explain stuff like the dress phenomenon that we talked about potentially as something which is in computer vision called color constancy, you can connect features that are much greater than the individual receptive fields of units, to construct objects in lower levels than that you would usually be constructed in. So, that's horizontal connections.

**Drew Linsley:**
Top-down connections would be a way for units between different areas or different layers of your CNN to communicate together. In order to construct a model of top-down connections, we found another task, which might be a good probe of that. So this is my colleague JK Kim who's now at deep mind, he's the phenol when it comes to constructing these tasks that might stump artificial intelligence models. We wind a dataset which would test grouping the ability to segment a scene in the absence of the kinds of features that were in Pathfinder.

**Drew Linsley:**
So in the absence of low level grouping features, gestalt features, JK went and found a dataset of letters, and the key point here was to perturb those letters in such a way. And this is in our paper called Disentangling The Neural Mechanisms For Perceptual Grouping. If you look at these letters, what you'll see is that there's really no low-level way, just looking at local features to figure out what the letter is. So, that's an essential point.

**Drew Linsley:**
The only way to recognize the letter is to look at the whole letter. Okay. So top-down feedback would be a way, for instance, of a region of visual cortex that is looking at a whole letter to tell a low level region that this letter on the left is an A, and this letter on the right is a B, okay? So don't confuse the low level features between this.

**Kanjun Qiu:**
Mm-hmm (affirmative)

**Drew Linsley:**
This was our test to see if we could successfully implement top-down feedback. We were guided again by neuroscience and data about the nature of top-down feedback in the brain. And indeed, we found that our top-down connections could solve this task, this letter task, which we call cABC, but could not solve the Pathfinder task and vice versa. Our horizontal connections could solve Pathfinder, but they cannot solve cABC.

**Drew Linsley:**
Now we have this model that's been stress tested with synthetic stimuli, so we're finally ready to move into the big league, but not really because we went incrementally. And so, I guess, this is an important point to make. One thing I've learned over the course of my postdoc is how important it is to align your task with the specific model hypothesis that you're testing.

**Kanjun Qiu:**
Mm-hmm (affirmative). Totally.

**Drew Linsley:**
After this, letters task, we moved on to a classic computer vision challenge called BSDS, Berkeley segmentation challenge. What's called contour segmentation challenge in which they had human observers look at natural images and draw contours onto the objects in those images. And so, why that's inappropriate task here is because these horizontal and top-down feedback connections have been associated in neuroscience with this contour detection style task.

**Drew Linsley:**
It's much harder to make the link to something like instant segmentation or semantic segmentation that people do in computer vision, but contrary detection, the link is already there. And so, we found our model can solve this BSDS task as well as humans, as well as the state-of-the-art, but it's much more sample efficient can learn in many fewer samples than the state-of-the-art.

**Drew Linsley:**
So this is the way that machine learning and neuroscience can work together so beautifully, in my opinion, is that we're able to understand why the biases that we're trying to model, why they would be useful for function. And so, specifically we found that when you optimize a model to not have these biases, that it performs worse, it's less able to do the contours.

**Drew Linsley:**
So now, what we have is, step-by-step, looked at biases in the visual system, which we believe reflect feedback processing. We've shown that those biases can give rise to a model for horizontal connections, which can solve this Pathfinder task, which stumps transformers today. And we've shown that when you extend it into a hierarchy, these feedback connections into a hierarchy for top-down connections, that you can dissociate the role of top-down in horizontal connections and we can outperform the state-of-the-art on these old school, computer vision tasks unlike BSDS.

**Drew Linsley:**
And then, in our most recent NeurIPS paper, we showed that when you solve technical issues with this kind of model, namely the learning rule, that you use to train them, then you can outperform, I won't say the state-of-the-art because the field moves so quickly, but at the time you can outperform the standards for a much more complicated task called instance segmentation in Microsoft Coco.

**Josh Albrecht:**
Yeah. I was going to say that paper, I think that was part of the reason that I met up with you at NeurIPS.

**Drew Linsley:**
Yeah. Right.

**Josh Albrecht:**
Which was really, really interesting. Do you want to give a quick description for people who at this moment may not have gone through the poster session?

**Drew Linsley:**
Yeah. At Europe's this year, we presented a paper called, Stable And Expressive Recurrent Vision Models. We tested the hypothesis that the current field of computer vision is dominated by feedforward models to convolutional neural networks instead of recurrent neural networks, because CNNs are easier to train and specifically they use less memory to train them recurrent neural networks.

**Drew Linsley:**
This is because the typical way that RNNs, recurrent neural networks are trained is with variants of backpropagation. So it's really the same thing as backpropagation, if you all are familiar with that.

**Kanjun Qiu:**
Back Prop Through Time. 

**Drew Linsley:**
Exactly. What that amounts to is you take your normal network, you pass a stimulus through the network, you keep track of all the activities through it, like you would in the CNN and then you compute the gradient and backdrop through it to update the weights. That's a usual CNN with backdrop through time, you have an RNN, so you're reusing weights over and over again.

**Drew Linsley:**
And the number of times that you reuse the weight matrix, you need to store that many times the number of activations in your model. It's only a linear complexity, but it kills you when you're trying to compete with the state-of-the-art and feedforward models.

**Drew Linsley:**
We realized that there's a classic learning rule in alternative to backpropagation through time called recurrent backdrop. This really dates back to find them, but was like everything else in the field reinvented back in the late 80s by Almeda and Taneda and they invented it simultaneously. So it's in two different papers, but they're given co-ownership of this.

**Drew Linsley:**
We wanted to understand if this algorithm could work in a vision models. And so, to cut to the chase, we found that it can't. It does not work in vision models because there's a trade off that we discovered. When you build vision models, you use nonlinear called linear rectifications, but more generally you use nonlinearities, which, on one end they're monotonically increasing.

**Drew Linsley:**
But when you build a recurrent network models, you desire something called a stability or contractive dynamics. And what this means is that eventually the output of the model, this recurrent output of the model, is going to reach a steady state where it will no longer change. Those two concepts, the monotonically increasing nonlinearity of vision models, versus this desire for stable dynamics are fundamentally at odds.

**Drew Linsley:**
If you try to apply this learning algorithm to vision models, it fails, for that reason.

**Kanjun Qiu:**
That makes sense.

**Drew Linsley:**
There's an easy fix, which is the chains on nonlinearity, but then you're stuck in a regime of sigmoide and tan-h/hyperbolic tangent, which are not expressive. Exactly. They varnishing problems, and they're not expressive enough. Our solution was to derive a regularization, essentially, which allows the model to adjust its stability and expressively online. We can drop in the same relue or in our case, we use a soft plus. There's a technical reason for that, which I invite listeners to read about in the paper.

**Drew Linsley:**
You drop in these monotonically increasing nonlinearities, and if this specific term, lost term starts to increase, then that is evidence to the model, during training, that it's becoming too expressive, it's losing stability. It's going to have this give and take over the course of training in order to maintain stability.

**Drew Linsley:**
And so, the cool part about that, you might think you're completely hamstringing your expressivity, so the models aren't going to perform as well, but that's just not the case. And in fact, we're able to outperform few forward models with fewer learnable parameters by using this learning rule. And then you get all sorts of really interesting byproducts. So going back to Pathfinder, we just look at a really simple model, the key with Pathfinder, once again, let me restate the problem.

**Drew Linsley:**
You are trying to tell if two dots are connected to the same line or not. So if you're a feedforward model, the way you solve that problem is through depth. Either you have really big filters, but that's expensive and not very smart because these are curvy lines and you want some nonlinearities in your subjectivity, right? Ideally if you're a feedforward model, you just build depth in the deeper models are going to perform better on this task because they can learn piecewise approximations of these curvy lines.

**Drew Linsley:**
If you're a recurrent model, ideally what you can do, is with a filter that's going to simulate horizontal connections, let me explain how this horizontal connections models work, because I think that practicality is interesting. So imagine that you have a two layer scene and the second layer is going to just be reapplied to its output over and over again.

**Drew Linsley:**
Let's say you reapply it 10 times. If you know how receptive fields are built in CNN's by applying convolutions over and over again, you're going to expand the size of the receptive field. This is a way to simulate interactions between units positioned at different locations over an image. This is, essentially, how the feedback model works. If you imagine that's how it works, then you can also imagine that you can really restrict the size of the filter of the second recurrent layer to be three by three, just so that you have... Or maybe two by two, some kind of width and height to it.

**Drew Linsley:**
What we found is that only when you use our learning rule, which balances, stability and express severity, can you take these horizontal canal filters down to their logical extent. And when you do that, then you can assimilate the model for hundreds of time steps in order to build up these highly nonlinear horizontal connection receptive fields and solve tasks like Pathfinder.

**Drew Linsley:**
That, in my opinion, is important finding one, which is that, now we show that when you pair recurrent models with this specific learning rule, you can become more perimeter efficient. The second interesting finding is that, when you train one of these horizontal connection models with this learning rule on a fixed size Pathfinder, and then test it on longer or shorter paths, then it's able to generalize to those zero shot. But you cannot do that if you use backdrop through time or if you use a feedforward model.

**Kanjun Qiu:**
Interesting.

**Drew Linsley:**
Okay. So, the inference there is that when you use backdrop through time and these monotonically increasing nonlinearities, you're not really learning a dynamical system, you are, but you're, overfitting that dynamical system to a specific depth. It becomes an all stats version of a feedforward model with just reusing the parameters in successive layers.

**Kanjun Qiu:**
That's right. That's right. And so what you've done is make it truly recurrent.

**Drew Linsley:**
That's right.

**Kanjun Qiu:**
That's really interesting.

**Drew Linsley:**
You're optimizing dynamical systems now.

**Josh Albrecht:**
One of the really cool things from that paper that I really loved was that you also apply them to the, as you say, instant segmentation task, I think, and the way that a flunk filling didn't naturally emerged, but there was no frame for it. Just like the way that you as a person would think about, "How do I segment this thing?" We all find one thing we score on the outline, but another one hadn't score on the outline, but this one filling feels like so much more of a natural way of solving this problem, which is really cool to see that come through in the algorithms. It expands the spill off the bubble of reasonable space that should be taken out by that object.

**Drew Linsley:**
That for us was a total surprise. And by the way, I just want to drop this reference. So Peter Wolf Semma is a brilliant neuroscientist out of the Netherlands who was a huge inspiration for this work. He has a paper in 2016, Testing Different Segmentation Strategies For Human Observers For Just Synthetic Images. And so, what they came to the conclusion in this paper is that they use a very similar strategy to what just fell out of this model of this flood filling.

**Kanjun Qiu:**
That's so fascinating.

**Josh Albrecht:**
Mm-hmm (affirmative). And really cool. It looked really good. One of the places where it failed is broke down and where those kinds of mistakes that a person would make, or an artifact of a setup.

**Drew Linsley:**
It's so far away from the performance of a human right now. So this is a challenge called Panoptic Segmentation and Microsoft Coco, and just to explain it completely in computer vision. There's generally two types of segmentation that people look at these days. If people don't really look at contour segmentation anymore, but what they do look at is semantic segmentation and instance segmentation.

**Drew Linsley:**
Semantic segmentation has no concept of individuation. What that means is you're going to paint every pixel of an image with a category label. Instance segmentation is identifying every instance in individuating those instances and identifying their labels. If you have a crowd of people, you're going to color in all the people with the people label, but you're also going to say that's person one, two, three, four, five, six, et cetera, et cetera.

**Drew Linsley:**
Panoptics Segmentation is a task which combines both of those and ask you to perform instance segmentation on the discreet objects in the scene, and then semantic segmentation on the other, what they call stuff.

**Kanjun Qiu:**
Technical word, stuff.

**Drew Linsley:**
Yeah. That is the term. The dirty little secret about Panoptic segmentation is that the performance of all of these models is really poor. So what you'll see in the papers is that people choose the same kinds of scenes to show. And these are usually scenes of people in cities. There's tons of training data on people in cities. And so these models overfit to that.

**Drew Linsley:**
But on other scenes, animal scenes, if you think about the wide variety of scenes, you could possibly want to do this task on, you're going to probably do really badly on most tasks. If any listeners are looking for a task, which is far from solved. And certainly if you're clever and reevaluate the benchmark in a way which emphasizes some of these classes, which are harder for existing state-of-the-art models, then there's going to be a lot of improvement that you can get out of the existing systems.

**Drew Linsley:**
For our model, I think, in general, what we found is qualitatively, you would suppress some of the false positives that you get from the standard that we compared to this feedforward FPN network. The really fun one that we've put in the paper is this scene of trains.

**Drew Linsley:**
And one of the trains has a zebra texture on one of the cars on it, this is like a classic CNN mistake where it's over-relying on the textures and it calls that zebra. If you look at the development of our models, because we can look at the time course of their segmentation, you will have false positives early in the time course, but sometimes, not all the time because it's way far from perfect, but sometimes those get overwritten as more context is brought into the algorithm.

**Kanjun Qiu:**
Ah, so adopt some shaped bias as over time.

**Drew Linsley:**
Yeah. So, shape bias is loaded. Really what happens, and we know this because it's by implementation, is the receptive field grows with steps of process. So if you have a small receptive field and you're looking at part of an object, it could look like something else based off of shadows, it could look like a face, for instance.

**Kanjun Qiu:**
That makes sense. So you're saying as content grows, what you're saying is really the receptive field grows, sometimes this model is able to tell that this is a train with a zebra pattern.

**Josh Albrecht:**
Mm-hmm (affirmative)

**Drew Linsley:**
Exactly. It can suppress some of these false positives, whereas the feedforward model is fixed.

**Kanjun Qiu:**
But there was something interesting. I'm thinking about what mental state must you have had or what theory must you have had in order to pursue this path of trying to develop an alternative to backup your time for recurrent visual models. And so, it seems like you've had some fundamental belief, maybe, tell me what you do actually have, or I'm going to have hypothesis of some fundamental belief that CNNs are not enough, feedforward networks are not enough, that's not actually how the vision system works. And instead recurrent models aren't necessary in the vision system. For something like this, what prompted that paper?

**Drew Linsley:**
Yeah. This is something I struggle with a lot because there's not many people that are pursuing this hypothesis, which is a good thing because you never want to be competing with the field. But on the other hand, maybe I'm completely off base. So, all I know is intuitively it makes a lot of sense to me that you would not want to optimize a fixed model on a dynamic world. That intuition only takes you so far, though, when you realize the computational cost of the fixed model.

**Drew Linsley:**
When I brought these results on the BSDS, a contour detection base said to my advisor Thomas, he asked me, "Oh, that's so cool. How many exemplars do you fit in your batch when you're training?" A little sheepishly, I respond, "One." It's not batch, it's, I guess it has mini batch of ones stochastically.

**Drew Linsley:**
So he made fun of me and we still got the paper published, which is fortunate, but this was in the back of my mind for awhile. We talked with people at Brown, in applied math. And so, I guess that's a fun part of this field. It's so engineering based and takes, without any qualms from so many different fields, bits and pieces of knowledge that you're looking for a solution to a defined problem.

**Drew Linsley:**
There are principles that you can look to. And certainly I was pointed in this direction by somebody else at Brown, Michael Frank, who's a leader in reinforcement learning who had heard of recurrent backdrop. But then you realize that applying these algorithms at scale is a whole different beast. Not just that, but applying them at scale and competing with the state-of-the-art.

**Drew Linsley:**
This is where the rubber meets the road, machine learning, because you try to develop theory, but you're constrained by the state-of-the-field. Everybody would love to publish their pet theories without worrying about evidence. The beauty of the theory will be enough to publish it, but that's just not the state of things. And so you have to balance the trade off of pruning away the theories that are probably impossible to implement right now and just pursuing those which might be able to, hopefully, challenge the state-of-the-art. But if not that, be similarly good while bringing new ideas into the field.

**Josh Albrecht:**
What are some of those theories that you have? Maybe don't want to have to worry about evidence to just, you have this theory. It seems like great, maybe not practical but …

**Drew Linsley:**
I don't have this theories, but I do want to mention that there's some really interesting work from Tomaso my advisor on synchrony. So there's this concept of neurons firing together or not how that based on information about stimuli. And so this is like an emergent phenomenon. It called synchrony, which is recorded in brains by neuroscientists, oftentimes it's about different frequency bands of process. And so, what I think Tomaso has pursued in the past is talking about how this could help in artificial intelligence.

**Drew Linsley:**
That's something where I'm not sure if the math is there or if it's an implementation problem or what, but, it's been a little bit hard to show those kinds of difference. I try to prune away those theories asap. What I've been focusing on though, is something maybe I'll run into that barrier motion models and spatial-temporal models, which is where I think that the brain can hopefully help out a lot because I think computer vision and AI is really hamstrung with the current approaches.

**Drew Linsley:**
A key problem in the field right now is spatial-temporal vision. That way this is typically done is you expand your 2D convolutional model into a 3D one. So you add another dimension to your kernels, which is just going to be hopefully encoding for some dependency between frames of the input. What folks quickly found is that it's really difficult to train deep 3D convolutional networks. So the common approach used these days is to start with weights trained on image net. So train for 2D object classification, and then repeat those in three dimensions.

**Drew Linsley:**
So you've multiplied or repeated or tiled out your weights and then fine tune those models on action video datasets. And it turns out it works pretty well, but I don't believe it works for the right reasons. So I think what is happening is that these datasets are relatively easy to recognize based only on static frames.

**Drew Linsley:**
So action recognition is turned into a 2D frame recognition problem. But the task of motion processing, I think, is absent from these models. And indeed, if you look at the filters, so there's theory on motion processing, visual cortex, and the concept is that you have different pools of neurons that are going to be tuned to space your temple statistics. So imagine that you have a baseball, but moving in a specific direction, you're going to have a neuron with a receptive field, extending through space and time encoding for that feature moving in that specific direction.

**Drew Linsley:**
This is something that you would hope to encode with the 3D compositional model, but it's very difficult to learn those tuned spatial-temporal features. Instead, what is learned is something called untuned spatial-temporal features. And so, there's also populations of these in the visual system, but essentially what you have, then, it looks like a flicker detector, basically.

**Drew Linsley:**
You have a vector describing the change across the time dimension, and then you have 2D frames describing the stuff in each of the frames. You can not modulator things in different directions, you can only change the contrast of the stuff appearing across those frames. So these kinds of separated spacial-temporal tuning is what is often found in these 3D convolutional networks.

**Drew Linsley:**
But striking is the tuned spatial-temporal features are found as early as in the retina. So you can look at retinal circuits and try to understand how you can build early tuning for those kinds of vectors.

**Drew Linsley:**
It's also found in the earliest visual cortical layer, V1, and then into dorsal stream motion processing areas. The brain doesn't use 3D convolutions either, so it doesn't use fixed size filters. That's just an implementation trick. And so, the hypothesis we're testing right now with some colleagues, is whether we can build recurrent models, which I think is a much more natural fit for the spatial-temporal domain, anyway, that can encode appropriate features, both tuned and untuned spatial-temporal features.

**Drew Linsley:**
Now where it's going to be difficult is, once again, competing with the state-of-art, because the field has a way of hyper parameter optimizing over the architectures that work best on specific datasets.

**Kanjun Qiu:**
Yeah. This is actually an area that we think holds the field back, which goes into my next question, but we have these really specific tasks that people really over-optimized for. And even when you have a much better approach or a better model that generalizes better and could lead to more general intelligence, like can't tell, because all the tasks in the field are like I brought mice.

**Josh Albrecht:**
Yeah. It was like a chain of three papers where someone made a paper three or four years ago on the state-of-set. I was a pretty good paper. Someone else made an album on top of that and tricked it out and made a lot more complicated. Someone else took two other health data networks and merged them together and then optimized…

**Kanjun Qiu:**
And now super complicated.

**Josh Albrecht:**
3% performance improvement, and now it's us to say, "Yeah. Good luck.

**Drew Linsley:**
That's the crazy part is the incremental improvements.

**Josh Albrecht:**
That's interesting.

**Drew Linsley:**
So what does that say? We're definitely using the wrong benchmarks. And so, there is always going to be an interest in developing more naturalistic tasks, but what's the ecological task for motion recognition? I don't know. I guess somewhat inspired by that question, I've started to work with colleagues on a game-plan. OpenAI has done some interesting work on developing a set of games, which is called Procgen procedurally generated game-plan.

**Drew Linsley:**
We're using that as a stand-in for these action recognition datasets to understand, if similar, types of models I'm alluding to these recurrent models can be plugged into games. And if they can give the trained agents better generalization that for changes to spatial-temporal parameters, for instance, changing the speed, the velocity, et cetera, et cetera of game objects at test time. So that's the kind of generalization we would expect to see if we can learn appropriately tuned spacial-temporal factors.

**Kanjun Qiu:**
Interesting.

**Josh Albrecht:**
I'm looking forward to it. I read one of your papers from, I think last year, one of the letters that was…

**Kanjun Qiu:**
Yeah. Disentangling?

**Josh Albrecht:**
That yeah. I was like, "Oh, wow. This is the same guy? Oh, interesting." Yeah. Does feel like you going to go your own direction. I think is a really interesting, unique direction for you, maybe, there are other people doing it.

**Kanjun Qiu:**
Actually, one thing I was wondering about is, what work of yours do you feel was most overlooked? You felt it was interesting, but it seemed like no one seemed to get it?

**Drew Linsley:**
I have a paper at ICLR called, Learning What And Where To Attend. I think this is very relevant right now with the explosion and transformers. At that time, what was big in the image classification field was called squeeze-and-excite attention. It's essentially gate, if you're familiar with those from RNNs, you add another module onto your convolutional layer, which has a different kind of nonlinearity and it's going to have a multiplicative interaction with output of your convolution.

**Drew Linsley:**
So, that's just a fancy way of saying it's going to suppress, to some extent, the activity in different feature maps of the compositional output. So there's these attention models, if you look at what the attention models are doing, it's completely idiosyncratic, it's uninterpretable, and yet the CNNs are getting little boosts in performance.

**Drew Linsley:**
And so, we had some pilot work which showed that if we looked at the feature map visualizations, gradient maps, or saliency maps, or what-have-you, of CNN's, the important features used to identify different object classes, what are you going to use to identify? A dog versus a cat what-have-you?

**Drew Linsley:**
Those are way different, qualitatively different, for machines CNNs versus humans. So now going back to the squeeze-and-excite, we thought, "Hey, maybe what we can do is take our dataset of importance maps from humans and use that to co-train attention in models." The interesting findings there were that when you do that, you get really interpretable attention maps falling out of the model. Attention can be constrained in these networks to look like a reasonable attention map.

**Drew Linsley:**
It improves performance, it improve sample efficiency of those models, but it also can be applied to a completely different dataset. So when you train on and optimize your model on image that with these attention maps and the attention data, then you test it on Microsoft Coco, which has many different objects, it's super high resolution, well, you get zero-shot generalization of attention maps to these images.

**Drew Linsley:**
Whereas if you do the same trick, zero-shot generalization with a regular CNN, the attention maps from it are completely uninterpretable. This generated a hypothesis fellow of a paper for future work, which is that attention really needs an additional source of supervision, other than the class label supervision that's used to train models these days.

**Kanjun Qiu:**
That makes sense.

**Drew Linsley:**
Yeah. And so, if you look at transformer attention, people choose these transformer attention maps, and tried to divine all sorts of interpretations of what's going on, it's completely subjective. And there there's no ground truth that's being compared to. So we already have this evidence that you need to do something special for attention.

**Drew Linsley:**
Going back to this paper, I thought, it was really nice because we introduced a dataset which provided an important constraint for models. We showed that humans in the loop had a use for an auxiliary task, rather than the primal classification tasks that people are usually using the humans in the loop for. And future work, I hope that people pick up on this dataset. I haven't heard a peep about it.

**Drew Linsley:**
We gathered 400,000 of these little attention maps, and we create a game to gather these maps, and I know if you look at individual attention maps that look relatively noisy, but when you drop those into the training procedure or average cross them, they give you these beautiful, smooth maps over these object images.

**Drew Linsley:**
So, for future machine learning work, I think that could be super interesting for neuroscience as well as, especially testing whether models of visual cortex can explain these attention maps and maybe explain encodings of attention in visual system. It's like a whole different research target than what I'm currently pursuing, but I love that paper.

**Kanjun Qiu:**
Interesting.

**Josh Albrecht:**
I also think that’s a really cool paper.

**Kanjun Qiu:**
Do you have any research ideas related to this that you'd want to donate to the community?

**Drew Linsley:**
We've been talking about biases. I think if you flip through an intro to psychology textbook, you get a lot of hints for potentially useful biases to explore for machine vision, one of these is emergent images. And so, this is, I believe, Lira Wolf who's at Facebook now developed the dataset of emergent images, which just describes essentially viewing a scene, but where all the important features in the scene have been replaced with dots. If that makes any sense.

**Drew Linsley:**
If you can imagine that in your mind's eye, so you no longer have color or contours or whatever, you just have a dot version of the scene where these dots are organized in just the right way so that, when you squint, you can make out the scene. So the classic example of this is the dog in the park. Lira Wolf has a dataset of these, and I think what would be really interesting is looking at the feedback mechanisms, that support perception of emergent images and trying to understand if those support any other shape perception, for instance, or any feedback mechanisms that might help with sample efficiency, generalization, et cetera, et cetera.

**Drew Linsley:**
Another example would be bistaple images. And so there's two classes of these. So bistable images would be an object where if you look at one way, maybe if you glance at it, it looks like one thing, if you look at it a little longer, it looks like another thing.

**Kanjun Qiu:**
Its like the fake face.

**Josh Albrecht:**
Mm-hmm (affirmative)

**Drew Linsley:**
Yeah. Exactly. I think on Twitter this week, there was the man hiking through snow, where if you look a little bit longer, it's a dog, this is what's called a bistable image. But what's interesting about that is you can have bistability at the level of individual images like these bunny duck or hiker dog, but you can also bistability at the level of people.

**Drew Linsley:**
And so, this is what people are finding with phenomenal, like the dress, which some people see it having different colors than others, the shoe, the crock, I think it is, as some people see it as pink, other as green, something like that. And so, there's these different phenomena of bistability, what kinds of neural mechanisms do those represent? Are those epiphenomenal? Or are they important? Are they here rustics of vision that can support a more robust processing that the world.

**Kanjun Qiu:**
It's really interesting. Those are really interesting questions. I really hope someone has solved them.

**Drew Linsley:**
Me too. Make my life easier.

**Kanjun Qiu:**
Totally. One thing I was wondering is, earlier we talked a little bit about areas of the field that you're interested in pursuing. What do you think holds them a little back?

**Drew Linsley:**
ImageNet, CFReD, and MNIST. These are things that hold the field back. It's more of a biproduct of conferences. So if you're publishing that in Europe's, ICLR, there's going to be a big emphasis on MNIST and CFReD, if you're publishing a CVPR, ECCB a big emphasis on ImageNet. One of the nuggets of insight that my advisory, Thomas Serre, told me, "Inducted biases can hurt you at times when they're not necessary for optimization."

**Drew Linsley:**
If you look at the field of computer vision, there was each-max which showed in primate visual cortex, how important a max-pooling can be for building up in variance that extended to simple computer vision datasets. But now these days on ImageNet, what people are using are resonant variance, let's say, max-pooling is absent from these models.

**Drew Linsley:**
And I think the reason for that, for the lessons of computational neuroscience of those being replaced with engineering, is because the engineers have found that when you take out max-cooling, you get a boost of 1% in top one accuracy on the validation set of ImageNet.

**Drew Linsley:**
What various groups have found is that you can explain performance on ImageNet through a pure texture bias of these models. I think there's a lot to local feature processing is what matters more than anything else when you're solving ImageNet. Same as CFReD, same as MNIST. You don't need any kind of complicated model from endless and yet the benchmarks of the field are MNIST, CFReD and ImageNet.

**Drew Linsley:**
So, this is a problem because if we want to develop better artificial intelligence, we really don't have the right benchmarks to do that yet. Now I think Microsoft Coco is moving in a good direction, but as we talked about, there's major biases in that as well. And that's evident in what kinds of qualitative figures that people plot with Coco papers. I think this is an open question of what to do, because I don't know what to do.

**Kanjun Qiu:**
That's great point generate all of your own data using a 3D game engine.

**Drew Linsley:**
I completely agree. I think that's why I went with Pathfinder and cABC, why I'm moving towards these RL projects with-

**Kanjun Qiu:**
The game.

**Drew Linsley:**
Game-play. And I agree with what you two are doing, I think that's the right way to go. But to an extent, because then you always have the gap where people will ask, "How well does your algorithm work when you move to natural image statistics?" And the truth is you don't know.

**Josh Albrecht:**
That's true. One of the things I think is actually really cool about simulators nowadays, is that the game engine is so good or we can actually try the realism dialogue all the way till... It looks realistic to me as a person, I can tell the difference.

**Drew Linsley:**
In your game engine?

**Josh Albrecht:**
Not in our game engine. 

**Drew Linsley:**
No. But if you look at Unreal 5.

**Josh Albrecht:**
If you look at Unreal 5. Actually there was a really good recent work where someone made a holed of realistic algorithm, like photo- realistic indoor scenes is what they meant. And so, I think I was-

**Drew Linsley:**
Oh yeah. I know what you're talking about.

**Josh Albrecht:**
It was really cool. Actually, that's really helpful. So I think within a few years we might actually be to the point where you can dial it up like that. Really see if it does transfer.

**Drew Linsley:**
Yeah.

**Kanjun Qiu:**
For people listening in the audience, are there any areas that you'd want to find collaborators in? Or anything else you want from the community?

**Drew Linsley:**
Yeah. Robotics is a field that I would love to move into. I think that is where they, by necessity, you have to emphasize a lot of the problems that we've talked about here. Sample efficiency, generalization, et cetera. And the current state-of-the-art is much more realistic than I think we're talking about in computer vision. They're limited to a handful of objects, max, that you can figure out how to grasp online.

**Kanjun Qiu:**
That's great.

**Josh Albrecht:**
This might also be a good time to plug your workshop that you’re organizing.

**Drew Linsley:**
Yes. I am putting on a workshop in ICLR, 2021, called, Generalization Beyond The Training Distribution In Brains And Machines. And this is co-organized with Xavier Boix from MIT, Judy Borowski at University of Tuebingen and Christina Funke, at University of Tuebingen and Matias Becker's group.

**Drew Linsley:**
So, we're going to have a full lineup of speakers talking about biological and machine learning approaches to this problem of generalization. So a lot of crosstalk between these different groups of people with discussion panels and talks throughout the day. And we also will have a call for abstracts, for posters, please submit and find us on Twitter at the ICLR 2021 generalization account.

**Kanjun Qiu:**
Awesome.

**Drew Linsley:**
All right.

**Kanjun Qiu:**
If you really enjoyed what was in this conversation, then definitely check out that workshop. Thanks a bunch too.

**Josh Albrecht:**
Yeah. This is really great.  

**Kanjun Qiu:**
This is really fun. I really enjoyed it.

**Drew Linsley:**
Thank you two, so much. This was such a pleasure for you to listen to me ramble and the little I heard about your work, it sounds fascinating. So keep up the awesome track of work.

**Josh Albrecht:**
Hopefully we will talk to again soon. 

**Kanjun Qiu:**
Yeah. And if we can ever help, let us know, feel free to reach out.

**Kanjun Qiu:**
Thank you for listening to generally intelligent. We love feedback and questions. So please feel free to ping us on Twitter at, @kanjun and @joshalbrecht. Or email us with any ideas of corrections. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify or your favorite podcast app. Thanks very much. And we'll see you next time.


