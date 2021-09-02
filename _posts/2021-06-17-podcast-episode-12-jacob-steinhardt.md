---
layout: post
title:  "Generally Intelligent #12: Jacob Steinhardt, UC Berkeley, on machine learning safety, alignment and measurement "
date:   2021-06-17 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-12-Jacob-Steinhardt--UC-Berkeley--on-machine-learning-safety--alignment-and-measurement-e12vsjf" width="100%" frameborder="0" scrolling="no"></iframe>

<br>

Jacob Steinhardt [(Google Scholar)](https://scholar.google.com/citations?user=LKv32bgAAAAJ&hl=en) [(Website)](https://jsteinhardt.stat.berkeley.edu/) is an assistant professor at UC Berkeley.  His main research interest is in designing machine learning systems that are reliable and aligned with human values.  Some of his specific research directions include robustness, rewards specification and reward hacking, as well as scalable alignment. 

His most recent [paper](https://arxiv.org/abs/2009.03300) at ICLR 2021 proposes a new test to measure an NLP model’s accuracy on a wide variety of tasks, ranging from mathematics, US history, law, and more.  It provides a measurement tool to help researchers specify an important problem: while current models can achieve superhuman performance on benchmarks, they lack the ability to understand language on a whole.  Another of Jacob’s [papers](https://arxiv.org/abs/2008.02275) at ICLR focuses on measuring a language model’s knowledge of basic concepts of morality.  It shows that current language models have a promising but incomplete ability to predict basic human ethical judgements.

**Highlights from our conversation:**

📜 “Test accuracy is a very limited metric.“

👨‍👩‍👧‍👦 “You might not be able to get lots of feedback on human values.”

📊 ”I’m interested in measuring the progress in AI capabilities.”


<br>
*Below are the show notes and full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
<!--more-->
<br />

### Some quotes we loved
> **[11:33] On the freedom of knowing how to communicate unusual ideas:** 
“But I had to learn how to write a good paper without having a template.  I think it required me to learn to become a significantly better writer. And I think that helped later on, because it made me feel more comfortable pursuing unusual ideas. I knew I had the skills to present those ideas.  As long as I believed in them, I could get other people to believe in them.”
>
> **[34:55] On learning hard phenomena from big data sets:**
“People have historically been interested in these parts, like compositionality of objects and occlusion...but thinking about these complicated things directly is just not really the right way to go. You just want this very diverse distribution of things that are deeply ingrained in evolutionary history as opposed to being part of explicit reasoning”
>
> **[21:10] Why measurements matters for AI safety:**
“I've been really obsessed with this idea of measurement. First of all, test accuracy is a very limited metric. What are we trying to do with it?  I'm kind of thinking in analogy with climate change as another field.  For a while, there was a lot of climate skepticism or climate denial.  At some point it becomes pretty clear, when there's regular heat waves fires and that sort of thing.  You probably wanted to do something about it before that point.  Having these more subtle measurements that you can look at are important. And the other thing is I think it actually laid the groundwork for the more extreme weather events to become a convincing signal.

<br>

### Show Notes
* Jacob’s original career plan and the exploration that led him to ML [01:40]
* Jacob’s first research area in grad school: computationally bounded reasoning [05:47]
* Pivoting to robustness research [09:16]
* How Jacob’s early research directions helped him learn to communicate unusual ideas [10:40]
* Two different types of adversarial robustness research and its significance [12:30]
* Gap year at Open Philanthropy and OpenAI [17:11]
* Learning about scaling at OpenAI [18:08]
* Working on Covid research and lessons [19:37]
* Working on measurement (not just test accuracy but other metrics) [21:09]
* Measuring AI capability jumps for safety [24:23]
* Measuring progress in AI capabilities - Jacob’s  [paper](https://arxiv.org/abs/2008.02275)  [27:14]
* AI calibration for prediction accuracy [27:55]
* A summary of different types of robustness [29:16]
* Dan Hendryck’s work with collecting data sets [30:39]
* Jacob’s most unusual  [paper](https://arxiv.org/abs/2008.02275) , measuring the ethics of AI models [33:19]
* What work has impacted Jacob most? (GPT-3, scaling laws for NNs) [36:23]
* Why does measurement matter? And Jacob’s interest in the history of science. [38:37]
* Filtering your information diet [40:17]
* Should researchers be hedgehogs or foxes? [42:25]
* What methods are underrated in ML research? [46:34]
* Jacob’s  [paper](https://arxiv.org/abs/1807.03341)  on troubling trends in Machine Learning Scholarship [47:49]
* Attributes of a great research lab [53:02]
* What makes for a great advisor? [56:07]
* What makes for a great researcher? [57:21]

<br>

### Transcript
**Jacob Steinhardt:**
Another thing that I'm interested in is just measuring the progress in capabilities, getting different AI capabilities seems important. Vision tasks just seem to be falling like flies. I don't know if there's any vision tasks that's survived for more than a year and a few tasks seem a little bit better, but I think those are also starting to fall like flies. I know we've come up with a few harder tasks. ML Systems are still not very good at math. Humans also aren't very good at math, but also not good at law it turns out. One thing we did was just get multiple choice exams in 57 different subjects and just measure all of them. I think that gives the kind of interesting, comprehensive view on broad domain specific knowledge.

**Kanjun Qiu:**
Hey everyone, I'm Kanjun Qiu and this is Josh Albrecht. We run Untitled AI, an independent research lab that's investigating the fundamentals of learning across both humans and machines in order to create more general machine intelligence. And this is Generally Intelligent, a series of conversations with deep learning researchers about their behind the scenes, ideas, opinions, and intuitions that they normally wouldn't have the space to share in a typical paper or talk. We made this podcast for other researchers. We hope this ultimately becomes a global colloquium where we can get inspiration from each other and where guest speakers are available to everyone, not just people inside their own lab.

**Kanjun Qiu:**
Well, welcome to the podcast. We're really happy to have you. To get started, I'd love to understand how did you develop your research interests and how did you get to working on the things that you're working on now?

**Jacob Steinhardt:**
When I started as an undergrad, I thought I was going to do math research. I think if I remember correctly my plan was to become a math professor and work on graph theory. My freshman summer I did this Math REU, which is this research experience where I did do a bunch of combinatorics stuff. It was actually pretty fun. Somehow it wasn't deeply satisfying in some way. I could tell stories about why it wasn't. It was more a gut level of where's the impact and a lot of the other people in the REU were a lot more socially conscious than me. So that got me thinking more about my place in society. And that caused me to also want to think more about the bigger societal impact of what I was doing. So at that point I felt I wanted to pivot away from theoretical math, but I didn't really know what to do instead.

**Jacob Steinhardt:**
So I actually took a bunch of different classes or a bunch of different areas. So I took some econ classes. I took some bio classes. I took this really awesome Cog Sci class like Josh Tenenbaum at MIT, took a robotics class. I didn't really know what I wanted to do. I thought all of those were pretty live options, but I think I eventually settled on a couple of areas that seemed more appealing to me that I started to do a bit of research in. One was the cognitive science. In other words, robotics, there was this competition called the mass lab competition where you're trying to build a robot that can pick up balls and put them in bins, which sounds really easy, but it's actually really hard because it has to be autonomous. Our difficulties were really at a much lower level than that.

**Jacob Steinhardt:**
It was like how do you build wheels? So we had this brilliant idea that we're going to have giant wheels because then we can roll over obstacles. But the problem is giant wheels have really poor torque ratio and small amounts of friction mean your robot can't move. I didn't know that really got me into robotics. And I think rather than including that I needed to learn basic control theory. I was like well, the problem with this was that it was just non-linear system. And so I needed to learn how to solve nonlinear control theory. So I took this graduate class on nonlinear control theory without having taken an undergraduate class on linear control theory, which was probably not the best idea, but that jumped me into robotics research as well. I think both cognitive science and robotics felt like they were suffering from a lack of basic foundations that seemed like they were really foundations of machine learning.

**Jacob Steinhardt:**
Cognitive science, there's all these models of human decision-making somehow artificial decision-making often helps shed light on that. And then robotics, it felt like a big problem was everything was much to hand designed or you wanted things that are more learned. That was one thing. It seemed like it had some very fundamental mathematics that got at a few other areas that had seemed quite interesting to me. And then the other was that it seemed at the time to me, at least that AI was in some way going to have a huge impact on the world within the next 50 or 100 years. This was in 2011 before everyone believed that. But I think there's just this basic argument that once you have something smarter than humans, that's going to be a super big deal. I also read arguments that it could be really risky and that there could be a lot of risks from it. I heard other arguments that it was going to be one of the best technologies that ever happens for the world. I wasn't really sure what to think there, but it seemed pretty important to get to the bottom of that. Either way it was a pretty leveraged thing to work on. So I decided to go to grad school in machine learning based on that. So that's how I got into the field.

**Kanjun Qiu:**
As you're interested in the social impact and the potential impact on the future. And then how did you end up working on the work you did in grad school and how has that evolved till now?

**Jacob Steinhardt:**
When I started out in grad school, I was working on an area that at this point is pretty esoteric called computationally bound and inference or commutation bounded reasoning that came out of the cognitive science influence I had because a big question with humans is okay, humans don't have that many CPU cycles. They have to follow all these heuristics. So, how do we have an account of these heuristics. At least at the time it showed up for machine learning systems because often you would have these tasks like say machine translation where you needed to translate an input sentence or an output sentence. There's a very large number of potential output sentences. So searching over all of those is quite difficult. The reason why this is esoteric at this point is that we mostly solved this issue with deep learning.

**Jacob Steinhardt:**
The solution now is we just build up the sentence word by word and use the hidden representations of the neural net to remember anything you needed to remember for more than one word to go, and then you're good to go and there's no search problem anymore, but at some point there was this big search problem. So that's when I started out working on, it was a very interesting area. I wrote a lot of papers on it that I quite liked, but I think it turned out to be a very poorly chosen topic in terms of timeliness. There are a couple of other areas I was interested in at the time. I was working on that partly because I already had ideas for what to do and probably having thought about it when I was an undergrad, but there were a couple other areas that I started to gravitate towards that were more based around understanding risks from AI.

**Jacob Steinhardt:**
So the first attempt at this was thinking about how to specify what an AI system should be doing. I was thinking of this first, just from a very traditional computer science-y programming languages perspective of like okay, well you often have functions that are supposed to be doing something. If you can write down these APIs that say what they're supposed to do, but if you want to do something like automated debugging or something like this or automated verification, you have to actually formally specify what each function is supposed to do. And it turns out that it's an enormous amount of work and not even clearly possible to go from this English description that you see in programming APIs to an actual formal description. So I spent a while thinking about this, but not making much progress on it.

**Jacob Steinhardt:**
One of my fellow grad students, Dan Selsa made a bit more progress on it than me, but I eventually drifted towards thinking about this a different way. We shifted from thinking about this formal specification because it seemed way too hard to just thinking about, okay, what makes software do what you want it to do? From that perspective we were thinking, okay, well, if it's well encapsulated in the sense that you know when it ought to work and know when it ought not to work, that seems good. What are the senses in which machine learning fails to live up to that? One way is this contract that your test distribution should be the same as your training distribution. This is pretty bad first of all, because it's a very stringent contract, but it's also a non-local contract in the sense that you can't tell from a single input output pair if the distribution of inputs is the same as some other distributions-

**Kanjun Qiu:**
To look at the entire set of inputs.

**Jacob Steinhardt:**
Right. People can't hold some giant distribution in their head. So I think that was one thing that pointed this notion of distribution shift or robustness as being an important current failing point of machine learning systems. The other one was thinking more about this argument that it should be difficult to get machine learning systems to do what you want, which fails in the sense that you could just give it data about what you want and train it to do that. The argument is what humans want is complicated, but the world is also complicated. So this isn't really fundamentally an issue. Well, the sense in which I think it is more fundamentally an issue is I might be able to tell you what I want in a bunch of situations.

**Jacob Steinhardt:**
So you might learn a good function that approximate that on that same distribution of situations. But then once you're in new situations, then this might not generalize and you can say, okay, well the same thing is true about just understanding the world that might not generalize, but that's not as true because you get to observe fresh samples from the world. Some people always get lots of feedback on predictions about the world and understanding the world, but you might not be able to get lots of feedback on human values, especially if you have ML Systems that are smarter than humans or acting out fast timescales where it's hard to get feedback. So that was the other thing that led me to robust it.

**Kanjun Qiu:**
Interesting. Do you feel like the work on compositionally bounded reasoning was helpful toward your work on robustness?

**Jacob Steinhardt:**
One thing is a lot of the ideas I was pursuing were a little bit off the wall, at least compared to what someone would do if they were just thinking about things straightforwardly. I think they're off the wall in a good way, but it presents a big communication challenge, especially if we're getting something accepted into a conference. So I had a lot of early conference rejections that I think were just due to not knowing how to communicate my ideas in a way that would be compelling to reviewers. Of course, it's always something you're going to have to learn, but I think it was harder here because there's not as much of a template. If you're writing a paper that's doing better on some benchmark.

**Jacob Steinhardt:**
There's been a bunch of papers like that written before, you have a template you can follow, but I had to learn how to write a good paper without having a template. I think it required me to learn to become a significantly better writer. And I think that helped later on because it made me feel more comfortable pursuing unusual ideas. They knew I had the skills to present those ideas. As long as I believed in them, I could get other people to believe in them.

**Kanjun Qiu:**
And so then you worked on robustness for awhile during your PhD and then after graduation and now that you're at Berkeley, how did that evolve?

**Jacob Steinhardt:**
I actually pivoted in robustness after two years, although it's like another set of things within robustness. For awhile, I was focused on distribution shift. I was trying to come up with all these theoretical models of distribution shift, how to handle them. I think there are interesting papers from that. It's not totally clear how successful that segment of time was, but that I pivoted towards more adversarial robustness and considered two different types of adversaries. One is this famous thing of adversarial examples that just perturb your test inputs in some way to try to full of classifier. But the other was adversaries that can affect your training data. I initially got into this from a different angle, which was almost like this human computer interaction angle where I just thinking, okay, if we want to know what humans want, we are going to need to get a bunch of data from people.

**Jacob Steinhardt:**
And so we needed skill ways of collecting data. The problem is going to be all these errors. So can we create error correction mechanisms? The original idea was all of a sudden error correcting codes for human crowdsource student feedback that somehow turned into thinking about how to handle data that could be corrupted in some worst case way. But we realized that the math for that just generalized to handling any corrupted training data, and that ended up at least spiritually cohering well with this other question of how to build adversarially robust models for neural networks. So that was my last two years of grad school was this nexus of questions. I think that ended up being quite successful. We had some really deep theory around these training time perturbations, but we also had some cool fraud verification work for the test time perturbations. I think all the work before that was also a useful part of my resume. But I think those last two years it was most of what got me a job in academia. So I think also one lesson is it's totally fine to pivot a bunch.

**Kanjun Qiu:**
Can you explain the significance of the results in those last few years?

**Jacob Steinhardt:**
Yeah. So let's see with this train time robustness, the basic question there is you have a bunch of data that you're trying to learn from but some fraction of that data could be arbitrarily corrupted. So you could think of that as outliers, or you could think of it in a more adversarial sense that as data poisoning and attack, where some adversaries creating fake data for your system, maybe by creating fake user accounts. And so the question is, how do I learn from this data in a robust way? You just naively do gradient descent. You can show that in the worst case, you're totally hosed. So are there better ways of doing this? This is a very old question. Statisticians thought about this a lot in the eighties, but they weren't thinking about certain scaling issues that I think computer scientists are maybe more sensitive to.

**Jacob Steinhardt:**
In particular, what happens when you make the dimension very large. So it turns out a lot of those traditional robust estimators scale, somewhat poorly with the dimension of the problem, which is no good in modern machine learning where the dimension could easily be in the millions. And there was a group of people at different universities that were thinking about these questions around the same time. The quick upshot is you actually can develop methods that do scale well with the dimension that let you get tough. That's like almost as good as if you hadn't add any outliers at all, but that is robust against these outliers. And that I think the one particular thing I worked on is that even if the majority of your data are outliers, you can actually still do something. You have to be willing to split your data though.

**Kanjun Qiu:**
Interesting. You have to first identify which ones are the outliers.

**Jacob Steinhardt:**
Well, you can't necessarily identify which ones are the outliers because the outliers could just look completely coherent data.

**Kanjun Qiu:**
You can still learn as if you had learned on a non-adversarial dataset.

**Jacob Steinhardt:**
Yeah. In this case, so you have to be willing to shard your model. So suppose two-thirds of your data could be outliers. You could have three equally sized data sets that all look reasonable. And then it's really not clear which one you should follow, but I can shard by model into three models each associated with one third of the data. And it could be I don't know which of these thirds is the real data, but one of them is, and one of these three models is the right one. Again, this is one of these things where it's not totally clear what the practical significance is, but it was pretty cool. I think that was definitely the most surprising thing to most people.

**Kanjun Qiu:**
And then after you graduated, how did you think about your work at Berkeley, your interests there? What felt interesting? What feels interesting?

**Jacob Steinhardt:**
So I actually didn't go straight to Berkeley. I took a gap year, which consisted of three things. So I worked at open philanthropy for four months, which is this nonprofit that does grant making in a bunch of areas, but in particular it's safe AI. So I just was interested in seeing that side of things then I spent two months just taking a vacation, also highly recommended. Then I spent six months at open AI. It was an extremely educational six months. It shaped a lot of my views. I got a lot of intuition, just how things work at scale relative to when I was a grad student, I'm much more interested in doing large scale experiments because I think often things you see at large scale don't show up at small scale.

**Josh Albrecht:**
Maybe another question related to the open AI experience. Can you give any concrete examples of the things that are very different?

**Jacob Steinhardt:**
One of the teams at open AI always assume called the clarity team that does a lot of cool visualization work. And I decided to just try all their stuff out on a bunch of models I haven't played around with, but that they definitely hadn't designed them for, just to see how it worked. And so there were these mini image net models, and then full-scale image net models. If you do the visualizations on the mini image net models, you don't get stuff that looks pretty good semantically meaningful, but on the full vision models, it looks a lot more meaningful. Even on CFR, you get somewhat meaningful images. But I think on all of these models, the early layers look edge detectors and color contrast detectors. And then sometimes the later layer is just look like mush.

**Kanjun Qiu:**
Do you have any hypotheses on why?

**Jacob Steinhardt:**
There's probably fewer ways to successfully make a very fine grain distinction than to make a more coarse-grained distinction? I just need to tell you if something's a bird or a cat. There's a lot of features I could base that off of.

**Kanjun Qiu:**
Or is if you're distinguishing between two breeds of cat. You need to pay attention to very specific features and you really need to pin down what features you're detecting. That makes sense. So you took some time off and now you feel has really impacted the way you thought about large versus smaller scale and then what happened?

**Jacob Steinhardt:**
Okay. So I started at Berkeley six months before COVID started, but most of my students have never been inside a computer science building at Berkeley.

**Kanjun Qiu:**
Oh my God.

**Jacob Steinhardt:**
There was three months where I just stopped doing ML work for the most part and I just worked on COVID actually. So starting in March, I was like okay, I'm working on AI because it's this technical challenge that gets at global societal risks. Now there's an actual global societal risk right in front of me, but the time is now. So someone's got to step up for humanity. I think it was a good experience. But what I found out is actually a lot of people are trying to step up for humanity. It was crowded enough that it wasn't really clear that the best ideas were rising to the top, at least on the timelines that mattered.

**Jacob Steinhardt:**
That did impress upon me, that the heroes of the day are generally not the people who show up when there's already a crisis, it's the people who have anticipated the crisis in advance and laid the groundwork to be ready for it. The real heroes are the people at Pfizer and Moderna who has spent 10 years developing mRNA based vaccines, the researchers, even before that. So that was this decade long enterprise obviously it does have a lot of commercial impact, but I think it's nowhere close to realizing its full potential yet.

**Kanjun Qiu:**
That's a really interesting analogy. And so now that you've pivoted back, what's most interesting to you?

**Jacob Steinhardt:**
Well, recently I've been really obsessed with this idea of measurement. First of all, test accuracy is a very limited metric. What are we trying to do with it? I'm thinking in analogy with climate change is another field where we have all these measurements of the global temperature and the temperature and all these different areas and we never implemented events. And you can see it going up for a while. There was a lot of climate skepticism or climate denial. At some point it becomes pretty clear when there's regular heat waves and fires and that sort of thing. You probably want it to do something about it before that point. These more subtle measurements that you can look at are important. And the other thing is I think it actually laid the groundwork for a little more extreme weather events to be come the convincing signal, because there was no framework for thinking about this as an increasing trend. I think you wouldn't necessarily notice some of these, you wouldn't tie everything together.

**Jacob Steinhardt:**
So I feel it was really important for climate change to have thoughts that are conceptually like okay, what are these things that we might be worried about? And can we build really good and reliable measurements of these things and how they're changing over time and even build a forecast of how they'll further change over time and try to get at some underlying mechanisms that predict whether it will be linear and non-linear. So this is something that I'm really excited about is just thinking about what stuff should we be trying to measure? Can we just come up with different measures of robustness and try to understand if they're increasing or decreasing over time, but then the question is, are these the right measures or is this probably actually easier or we should be working on something else.

**Jacob Steinhardt:**
If google image net test bed, there's this cool paper by some other people at Berkeley that just takes all the different robustness datasets that have been out there. And it's scatterplots in distribution versus out of distribution accuracy for hundreds of different models. So you can really see trends. They have this nice web UI that does this for you.

**Kanjun Qiu:**
Interesting. Did you learn anything from looking at this?

**Jacob Steinhardt:**
I feel like I had looked at all this data long enough before it existed.

**Kanjun Qiu:**
Yeah. You already have a sense.

**Jacob Steinhardt:**
But I think it has made it much easier to convey those points to other people. If you can just show it to them.

**Kanjun Qiu:**
What are some of the measures that you feel are most interesting or surprising or promising?

**Jacob Steinhardt:**
Yeah. So I think measuring robustness is one. Another thing that I'm interested in is just measuring the progress in capabilities, getting different AI capabilities seems important. Vision task just seem to be falling like flies. I don't know if there's any vision task that's survived for more than a year and a few tasks seem a little bit better, but I think those are also starting to fall like flies. I know we've come up with a few harder tasks. ML Systems are still not very good at math. Humans also aren't very good at math, but also not good at law it turns out. That's also a pretty tough area that most people can't do. This is reading a complicated legal contract and saying whether this commits one of the parties to nonbinding arbitration with the other party, like understanding when you might get capability jumps, because I think everything improves smoothly then everything's very predictable. But if you have a jump, then I think you should be more worried about that.

**Jacob Steinhardt:**
I've been trying to think more about machine deception, still been trying to think of a good way to measure it. We talked about this idea earlier, if you would use human labelers to say what people want and use that as a signal for the ML System, but people are noisy and sometimes knowing what you want requires prediction consequences or something that might be hard to predict. ML models are not really incentivized to fight humans with things that they'll be happy with, but things that say they would think that they'll be happy with or seem good to them, but maybe aren't good in the long term.

**Jacob Steinhardt:**
It seems important to characterize that. And one thing you could imagine doing is having people that you hate to think for increasingly long periods of time. If I'm training with a person that's thinking for one minute, can that generalize to a person thinking for 10 minutes to an hour, because there's some point where you're just good to go or do you always eventually do some form of deception? How does that scale as models become smarter? This is something that I personally really to keep my eye on. And actually, I don't think we have any super good measures of this right now.

**Kanjun Qiu:**
Interesting. So I understand what you're proposing is in measure where you have people think for increasing amounts of time about what objective they want and then how different are the two years objectives from the thing for one minute objectives. That's an interesting manner.

**Jacob Steinhardt:**
The concrete thing would be trying to decide what articles to give it a newsfeed. The simplest thing is as someone click on it after one second, ask people to think for 30 seconds about why they actually liked this article. Ask them a week later because sometimes people get fooled by fake news, but maybe you eventually figure it out.

**Kanjun Qiu:**
I see in order to determine whether the person actually got value out of it, over the longer period of time?

**Jacob Steinhardt:**
Yeah.

**Kanjun Qiu:**
I see. Are there specific measures for robustness and also for capability jumps that you think are interesting?

**Jacob Steinhardt:**
I think there's so many faces one for robustness. There's a few other ones, but I think those are probably the best we have right now. The main downside is there's nothing really weird in them. So a solution that generally works right now pretty well is you just, pre-train on a lot of unlabeled data, but I think that might break down if you had weird distribution shifts that aren't captured by your unlabeled data distribution. So I think that's the limitation that would be interesting to explore. Sometimes capabilities are pretty broad, but one thing we did was just get multiple choice exams in 57 different subjects and just measure all of them. I think that gives the interesting comprehensive view on broad domain, specific knowledge. For that lots of other people have done stuff that's more generalist knowledge, physical common sense and things like that, which are pretty interesting. You just have to think through what capabilities you care about.

**Josh Albrecht:**
I think that paper had one of my favorite plots that I've seen recently and it was a good plot of accuracy versus something else and then there's two labeled arrows and one part is pointing out the very high accuracy on marketing questions. It's oh look, machines are really good at marketing questions and there's a low arrow pointing up to oh, they're really valuable for more logic.

**Kanjun Qiu:**
And it's not good at predicting its accuracy on marketing.

**Jacob Steinhardt:**
Yeah. Lack of calibration is definitely concerning. That's another one of those thorns in my side of why are these models so uncalibrated, it feels it should be easy to fix, but there's a couple of simple ideas that help a bit and then nothing else helps.


**Josh Albrecht:**
Why does it seem like it should be simpler, it actually seems hard to me?

**Jacob Steinhardt:**
To be calibrated?

**Josh Albrecht:**
Yeah. Given that it doesn't understand what's going on, just gets a bunch of tokens. It almost feels there's a mismatch. It's predicting words. It's like calibration comes from words, but our understanding of calibration accuracy comes from at a different level.

**Jacob Steinhardt:**
Models are very statistical, they're trained on log probability, which is supposed to incentivize calibration. So in that sense, you would hope that it's calibrated. It's not clear that you should think it's trivial to do this. Actually I think I used to think coloration was really hard. And then for some reason I've shifted to feel it should be easy, but clearly this is a bad direction for my intuition to shift because it's really not correct. The frustrating thing is there's really no incremental progress on it. They're really one or two ideas and then a bunch of dead ends that didn't go anywhere.

**Kanjun Qiu:**
Can you give a brief summary of the many faces of robustness just as we've been talking about it?

**Jacob Steinhardt:**
Yeah. So the starting point was entering into a debate about what, if anything, makes models more robust, where there had been a bunch of different arguments in the literature. Some that are just nothing helps and some that are like here's some things that help, but what helps I think people disagreed about. And so you could try to litigate this on the couple of benchmarks that are already out there, but it's just going to be much more valuable to add more data points. So we just collected three more robustness benchmarks, which doubled the number of benchmarks. They were also a bit more diverse. They had things geographic shift and temporal shift, which were not obviously in the other benchmarks. And then we just systematically went through these seven different hypotheses to see which ones stood up. So it was a very science-y paper. And I think also goes in with this measurement theme, which is, you can have a bunch of verbal debates, but often just adding more data points is going to be a lot more valuable in terms of moving the conversation forward.

**Josh Albrecht:**
Yeah. Actually I really appreciate that about a bunch of your works. It feels there's a lot of them that add a new data set or many new datasets pointing out the math one is another one that you gave an example of. I think there was an ethics one. There was a tasks one.

**Jacob Steinhardt:**
Yeah. Most of the credit for that should go to Dan Hendricks because he's the student who's been collecting all these data sets and he was collecting them before I should have at Berkeley. And I'm sure he'll continue collecting them after he graduates. And then I don't know what I'll do, I'll probably stop collecting data sets because I won't have a student interested in it, but he's done a lot of really great work in that area.

**Josh Albrecht:**
Do you really think you'll stop collecting data sets after that? Or do you think that someone else will pick it up?

**Jacob Steinhardt:**
It's hard. It's a lot of work and it's not always glamorous and I think it's also easy for it to flop. I don't think it's a given that a data set will count out well. It's not a thing that it's easy for people to enter into. I do think the thing that I'll continue to do is collect phenomenon maybe. Maybe what's the difference between a data set and a phenomenon? The adversarial examples are a phenomenon that didn't necessarily require looking at new data, but involved a query and models in a new way. So I think that's something that I definitely want to do a lot of. Some of this machine deception stuff you could think of from that perspective, some of it would just involve collecting new datasets because you need the human labels. Although it might not even look a dataset, it might look more something more dynamic because you've got continuously getting human feedback.

**Jacob Steinhardt:**
But I think you had also imagined ways of trying to get out of this phenomenon without necessarily collecting a bunch of new data rather than having actual humans. You could try to use with student teacher models. Do you think of the teacher as the supervisor and you would have smarter and smarter teachers or things that? The problem with data sets is you're hostage to a community of whether people find it interesting enough to climb on that benchmark. But if you're just trying to collect data to understand something, you're less hostage to that as long as you learn something interesting. Some of the stuff I've been doing with Dan also is more along these lines of just trying to forecast capabilities rather than necessarily expecting people to climb on it as a standard benchmark.

**Kanjun Qiu:**
So just so I understand your distinction between datasets and phenomena. Phenomena is patterns you observe in model behavior and in datasets. And you're trying to identify classes of patterns. So adversarial examples that you mentioned earlier, or time consistency of values.

**Jacob Steinhardt:**
Yeah. That's right. Sometimes the data sets a good way to get out of phenomenon. It doesn't have to be that way.

**Kanjun Qiu:**
Cool. What do you feel is your most unusual paper?

**Jacob Steinhardt:**
Maybe the ethics paper actually.

**Kanjun Qiu:**
Tell us about that.

**Jacob Steinhardt:**
Well, so this was this dataset we collected of just a bunch of moral judgments and we were trying to train ML models to predict those judgments, but the paper was written very differently from a standard benchmark paper. Usually they would be okay, here's data. Here's how you collect it. Here are the baselines. There was a lot of moral philosophy in the paper. A lot of it was an argument for why these were the right ways of measuring ethical knowledge in ML models or light this task got at this underlined question. The citation list is pretty hilarious. We cite Play-Doh we cite Justinian. I forget who else. But the reference list is pretty hilarious. So we're specifically issuing this moral ambiguity where you pick these weird thought experiments, these trolley problems, style things, and really trying to pick things that are very common sense, deeply rooted in people's psyche and pretty system one.

**Jacob Steinhardt:**
They don't require a lot of reasoning because I think also a lot of philosophers are overly into these very analytical situations. I think the idea here is the history of ML is that these common sense things actually tend to be surprisingly hard, but they're also the right starting point. In computer vision, people have historically been interested in these parts compositionality of objects and occlusion, these difficult phenomena, which actually do show up in natural images. But it turns out that it's just image that is just a really good image dataset. You do end up having to deal with some of these implicitly. But thinking about these complicated things directly is just not really the right way to go. You just want this very diverse distribution of things that are deeply ingrained evolutionary history as opposed to being part of explicit reasoning.

**Jacob Steinhardt:**
So I don't think this data set or image net is the final answer in either of the domains. This is the starting point that then lets you build on to other things rather than trying to go directly for object permanence.

**Kanjun Qiu:**
What I loved about this paper is that every evaluation, every piece of data is so clear. Every statement is so clear. It's so intuitive. The data set is crafted in a very thoughtful way.

**Jacob Steinhardt:**
I want to claim at least 70%, if not more of it was just thinking about what the tasks should be. Basically all of the credit to that should go to Dan and Collin Burns was the other lead author on that. But I think they both have maybe minors in philosophy or at least took a lot of philosophy classes. So it ended up paying off in this particular case.

**Kanjun Qiu:**
What work do you feel has impacted you most? Or what papers do you feel you've spent a lot of time meeting or digesting?

**Jacob Steinhardt:**
Well, the GPT-3 paper would be one just because it was very surprising to me. How will it generalize the distribution. Having worked on robustness, one of the reasons I got into it is because ML models just didn't seem to be doing very well at OD and it seems there is still maybe worse OD. It just really seemed like you'd overcome a lot of that with lots of data. That was surprising to me and reframed how I thought about a lot of things. I think also a related set of papers on scaling laws for neural networks has been pretty influential. So it shows that they have this power law scaling in terms of performance of the function of other resources. One way it's influenced me is from a theoretical perspective, but there's a lot of classical math on a non-parametric statistics that actually reproduces some of this power law behavior but the exponents in high dimensional settings are horrible,

**Kanjun Qiu:**
Like low exponent in the high-dimensional settings?

**Jacob Steinhardt:**
Yeah. It's one over D in D dimensions. So if you're in a million dimensions, then N to the negative one over a million as a function of new amount of data, which is pretty bad, right? That means if you have to increase your data size by a factor of two to the 1 million to decrease the error by a factor of two. And so I had totally given up on that and interesting way of analyzing anything because that seemed totally bonkers. But the interesting thing about barrel, that's the exhibit, this powerless scalene, but the exponent is not great, but 0.05 is one of the lowest exponent I've seen. That's still not amazing. You need to increase by two to the 20 to decrease error by a factor of two. So that's a million fold perfector too. We increase model sizes by a factor of 10 every year. So you only have to wait six years to have your error. So that's not awful. It's not great either but this 10 X trend is probably not going to continue forever. The one book that I think everyone should read is Structure of Scientific Revolutions by Thomas Kuhn.

**Kanjun Qiu:**
What do you feel you got out of it?

**Jacob Steinhardt:**
Well, just the idea of a paradigm. So he talks about how fields progress between this puzzle solving phase and then this paradigm shifts where everything falls apart and gets rearranged. And I think it's a little more complicated than that. I think there's actually often those mini paradigm shifts that don't pull or feel of heart, but like this scaling law thing that how it's changed how people like me think about these problems. The information we get is extremely filtered by our paradigm and also the way we process information.

**Kanjun Qiu:**
It's really interesting a neuroscience study where it shows that basically whatever you believe to be true. So if you have a certain belief that makes a certain prediction, then you'll basically filter all implicate through this belief. As a very concrete example, it shows a pressboard of gray and white press squares, and then it puts some 3D shapes on the chess board and there's a light source. It gives a shadow shines on the 3D shapes and causes a shadow to be projected on the chess board. You look at this 2D image and you're asked about what color are the gray squares in the shadow and outside the shadow. And they look totally gray square in the shadow looks dark. So you're well, the degree screen in the shadow is dark. It turns out that the exact same pixel value, but because you expect that there is a shadow there, then the information that you're getting has been filtered. And so this appears to happen, not just visually, but with non-visual beliefs and predictions as well.

**Jacob Steinhardt:**
Yeah, I think that's pretty interesting. I think it's probably useful for thinking about just our overall information diet, amazingly every new source is a filtered source of information, for instance. So I think just thinking about what those filters are, is quite useful. I generally try to think how the information I'm getting is filtered but also how my processing of it is going to be filtered and you realize things you wouldn't have realized otherwise if you do this exercise. The couple of other history or science books I liked a lot, one is called The Eighth Day of Creation. It's about a molecular biology from the forties to the seventies. That's what actually really got me thinking about measurement because in molecular biology, for instance, x-ray crystallography, as one example really changed the field quite a bit. I definitely recommend that people read that book.

**Kanjun Qiu:**
Interesting. It actually reminds me of in physics, Newton and Galileo, they are not necessarily just great physicists, but they were also great lens makers. And so being able to make much better lenses, allow them to have better measurements, but it would improve the new measurement tools led to a lot of the breakthroughs.

**Jacob Steinhardt:**
Yeah, that's right. And I think Rosalind Franklin was probably the best crystallographer just in terms of the experiments to be really high quality at the time she was at the forefront of those discoveries. Crick's also an interesting case to think about because he really isn't an experimenter at all, but he just read basically every paper, he just knew all the experimental results of everything. And he was this aggregator.

**Josh Albrecht:**
Yeah. I think the idea of better measurement for the neural networks certainly resonates with me as well. I think being able to have more measurements and more understanding and more introspectability of models is also pretty useful for training them like why is this thing failing? Is this information contained in this model that I'm doing like ways of tearing things apart and debugging and figuring out what exactly is going on, I think can make it a lot easier. Otherwise there's such black boxes that it's hard to debugger or make progress in some cases.

**Jacob Steinhardt:**
Well, one thing I've actually been trying to think about is whether you should be a Fox or a hedgehog, if you're a researcher.

**Kanjun Qiu:**
Can you explain the difference between the two?

**Jacob Steinhardt:**
I don't know if Phil Tetlock came up with it or someone else and he just borrowed the term, but the idea is hedgehogs generally have this one big idea that they're really pursuing, they're super opinionated, pushing that one idea forward. Foxes are more aggregators. They have a lot of views. The views could change on any given day. They're trying to simulate the views of as many different smart people as they can dean which ones feel most relevant to a situation or have stood the test of time the most. They're not going to be clinging into one viewpoint. They'll just be okay, here's a few different ways of looking at this problem and let's see what all of them have to say. So there's a lot more fluid and it's a lot more aggregated.

**Jacob Steinhardt:**
First of all, I think foxes are just generally more right about things. Do you want to have accurate beliefs? You should just be a fox, but on the other hand, hedgehogs might be more likely to really change how people think about something. They might not get much out of it for themselves because they'll be wrong about so many other things that they don't get very far with it. But I think in an idea marketplace, that could be fine. You could still have a huge impact even if you're wrong about many other things. Do you need the foxes to then aggregate that into all of the other ideas, but they're not necessarily the creators.

**Kanjun Qiu:**
What do you think of this?

**Jacob Steinhardt:**
I don't know. It makes me think that maybe the place to produce value is to do this hedgehog, but it doesn't feel intuitively very appealing because it means I'll almost certainly be wrong about most questions feels like they should maybe be some better middle ground. One thing I've been thinking about is while you're working on a problem you want to be more of a hedgehog.

**Kanjun Qiu:**
Because you can zoom out and be more fox like.

**Jacob Steinhardt:**
Yeah. I tend to take a Steve Job's approach when I'm working on a problem, which is, I'll talk to a bunch of people and be like, "Oh, I'm working on this problem that I think is important." And they're like, "Oh yeah, you should do X." Assuming you're working on a problem that actually matters. If their ideas were good, then they would have solved the problem. And it wouldn't be a problem anymore.

**Kanjun Qiu:**
My feeling is that the fox hedgehog thing is a false dichotomy that you want to spend some time aggregating, but also if you're only an aggregator, then you become very boring person. Research doesn't come only from aggravation. You have to feel, develop much deeper ideas in a direction or in a few directions that are beyond what other people are developing.

**Jacob Steinhardt:**
That feels appealing to me. But I'm just thinking of examples, take like Nassim Taleb. You just really counted on this power laws are important thing. At a time I think before it was an obvious truth and in some sense hedgehogs are going to be the victim of their own success. If you're a very successful hedgehog, you're also very important. All he ever talks about is how our laws are important and antifragility is important. Everyone has these concepts in their head because they've been so successful. And then he wants to apply it to everything even when it's not very relevant. Have there been comparably, successful people who are more balanced foxes, even though they have hedgehog tendencies, is Elon Musk a hedgehog or a fox?

**Kanjun Qiu:**
I think all CEOs are some combination of both. I feel like I have to be both. I have to integrate a bunch of ideas and I have to push forward a direction that is unusual.

**Jacob Steinhardt:**
That's fair. Yeah. Bill Gates seems very fox like and he's very successful. Maybe you think he's also a hedgehog.

**Kanjun Qiu:**
He's probably hedgehogging into some areas. I'm sure there are areas where he can really push us forward into thinking. All humans are a bit both, it's like a false dichotomy.

**Jacob Steinhardt:**
Though we can call it a spectrum and then it's like where do you want to be on the spectrum?

**Kanjun Qiu:**
Well, actually something I was curious about is do you feel there are underrated approaches or techniques?

**Jacob Steinhardt:**
One just methodological thing that I think is really underrated is just exploring all the axes of variation in whatever setting you're considering. For instance, it's trivial to just rewrite everything again with a different random seed. This could be how different the numbers look. And actually sometimes things that look trends go away easily when you do that or just run it on an additional data set or try additional model. Computation is cheap these days, right? It's not like neuroscience where you have to do surgery on a mouse brain every time we want to try a new set in. The amount of time you spent prototyping and getting stuff to work is 10 X at least the time it takes to run your final set of experiments. So you should at least be trying 10 different settings because you definitely have the copy of detail resources to do that. And probably more than that, because again, it just requires letting things run. I think this is starting to become more common, especially in NLP, which seems to put a lot of emphasis on methodology, but it's really not ubiquitous at all.

**Kanjun Qiu:**
Yeah. Some of the people are on troubling friends in machine learning scholarship. What you just said reminds me of this paper.

**Josh Albrecht:**
I thought it was an interesting paper. One of the questions that I had was, did this have any impact? This was a year or two ago because I feel the trends that you highlighted, I still see, so have it gotten better.

**Jacob Steinhardt:**
Well, I feel like a lot of people have read it and reacted to it.

**Kanjun Qiu:**
What were some of the reactions you got?

**Jacob Steinhardt:**
Well, a lot of people are I'm glad you wrote this. They are very concerned about these trends.

**Josh Albrecht:**
Maybe just for our audience, the four trends in there were one failure to distinguish between explanation and speculation, two failure to identify the sources of empirical gains, for example, emphasizing unnecessary modifications to neural networks and actually the gains come from hyper parameter tuning. Three was mathiness, the use of mathematics to obviscate or impress rather than actually clarify, for example, by using confusing technical or non-technical concepts. And last the misuse of language, for example, by choosing terms of art with colloquial connotations, by overloading established technical terms, it's basically using words that you probably shouldn't have used to make it sound a little bit better or different or closer to something you're already familiar with. And those were the trends. I still see all of those in papers today. I'm not sure if it's actually gotten better or worse over the past few years.

**Jacob Steinhardt:**
I feel like I have to fight against it a lot when I'm writing papers, especially if it's with a junior student who's really excited to get their first paper out. Are you going to tell them to go back and do everything more carefully? I generally try to do that. And it really requires a conversation. And I don't think it's easy. I think it's more for the next generation. I think I've gotten emails from first and second year grad students who are reading this, it feels to me at least like they feel very passionate about doing things the right way, giving people the guideposts to go from with that can be good. Documents like this are a good starting point. Potentially we should have more of them or it should be more ingrained in general machine learning pedagogy.

**Josh Albrecht:**
I think each of those things helps in a review's sense. Not exactly, but a little bit, or it's at least more similar to other papers that other people have written or if you have some fancy math and someone reads it and they don't quite fully understand it, they might be like, "Yeah. Okay. Yeah. Sounds good enough." If you just say, "Oh, all of our gains came from hyper parameter tuning and not from our fancy thing." It's pretty hard to get your paper published. Maybe I'll place to push for some of these changes that might be in the actual review processes themselves.

**Jacob Steinhardt:**
Yeah. I think reviews processes still really disincentivized measure in scientific claims.

**Kanjun Qiu:**
You mean they incentivize extreme claims as opposed to major claims?

**Jacob Steinhardt:**
Yeah. I just need to make a compilation of some of the worst things.

**Josh Albrecht:**
We should, but I think that'd be fun. If you want, you can make the compilation and send it to me and I'll publish it anonymously. So you don't have to get a bunch of flack from other people because I think it'd be a worthwhile endeavor for sure. There are some egregious ones.

**Jacob Steinhardt:**
One of them was the question is novel and unanswered, as far as I'm aware, however, the results don't seem particularly surprising. I know we have some scientific question. We were here's the thing you might think. Is it true or not? I forget if the answer is yes or no, but they were like, "Yeah, this just isn't surprising." I was like I bet if the answer is a no, it would have also not been surprising. But the point is, it's 50/50 inferiority.

**Kanjun Qiu:**
You have no prior of course you're not surprised.

**Jacob Steinhardt:**
Yeah.

**Josh Albrecht:**
But that's the most important thing to learn, right? We have maximum uncertainty. We're learning the most thing.

**Jacob Steinhardt:**
Yeah. I don't know if you feel like well, it just seems like figure models are better, there's no other clear trends. Well, that could just be how the world works. I think there's also this bad traditional, since we can't do that, then how you do exciting science? Well, it's exciting if you take down someone else and so you always need to prove someone else wrong. You can't just be building up knowledge. Of course he thought the same thing, but it's just different framing. Someone came along and tried to answer question X made some progress. Some of the things they said were right and some of the things they said were wrong. Now we're adding to this Steve Bunkie and person X. I've also written papers that way. It definitely is the more exciting way to write them, but I'm not sure if it's the tone we want to set in our field. You should be adversarial and you argue with people and say when things are wrong, but that shouldn't be the incentive. The incentive should just be to figure out what's true.

**Josh Albrecht:**
Right.

**Kanjun Qiu:**
Very strongly agree.

**Josh Albrecht:**
I think it's one of the things that everyone agrees with in spoken sense, but then it's still sometimes happens. I think it's taken it's point.

**Jacob Steinhardt:**
There's no genuine spectrum. There's an extreme where we're all just kumbaya around a campfire. And I don't think that's where you want to be either. You do need to criticize other people's ideas. I think it's just that it shouldn't be one of conditions for publishing a paper. That's where I think it becomes problematic.

**Josh Albrecht:**
Maybe one other question I do like to ask, have you ever been part of a research group that you felt was really effective and what were some attributes of that that made it more or less effective?

**Jacob Steinhardt:**
Oh, yeah. I have been to a bunch of groups and there's definitely ones that I've liked a lot. I worked in Russ Tedric's group, which was a robotics lab. I think there were a couple of things that are pretty good. One was like we're just all in this one big room. So it was very easy to collaborate. Sometimes I've been in that environment and it's really distracting, but the thing that was nice, it was actually quite a large room and all of our desks went around the perimeter and in the middle where a bunch of robots and stuff. By default you actually weren't near anyone because you were just near a bunch of robots and maybe there was someone adjacent to you, 10 feet away in each direction. It felt quite spacious. But then it's also very easy to go talk to people. But also you're not getting as much noise pollution from people on the other side of the room. Somehow it's just perfect for promoting collaboration without creating distractions.

**Kanjun Qiu:**
What you say about space is really interesting.

**Jacob Steinhardt:**
Yeah. I've never found another space that was as good as that space. It was in this data center. So Frank Gehry did something right. I would love to find another space like that. There's something about the culture that I thought was also pretty good, but we had group meetings. People are just very engaged. There's just a lot of discussion. You usually only got halfway through your slides unless you were very attentive to that. I thought it really led to deeper discussions. I think maybe it's good to also get through your slides, but somehow most seminars I've been in have much stronger politeness norms where people don't really get into things as much. But I think it was also important that it was a tight knit group. It's just a seminar of 40 strangers and some random person is not letting you get past slide 3 like I feel like that can be a lot more annoying, but if it's someone you know and also you feel comfortable telling them to shut up so that you can get to slide four. I think it works a lot better.

**Kanjun Qiu:**
That makes sense.

**Josh Albrecht:**
Yeah. I think that's pointing something really interesting. Yeah.

**Kanjun Qiu:**
Are there other processes you've seen be really effective?

**Jacob Steinhardt:**
Well I liked Chrissy's group a lot in grad school. I felt like there there wasn't anything as special on the group wide front, but just on one-on-ones I think he held us all to very high standards, really with pick apart your ideas and make sure you have a very clear motivation for the projects you were working on. I think that's something I try to do. That's quite challenging. First of all, just because it requires a lot of mental bandwidth on your part doing it in a way that's not discouraging like somehow tearing people ideas apart, but in a way that makes them actually want to fix them rather than give up. I don't think it's an easy thing to do.

**Josh Albrecht:**
Are there any of those attributes of what do you think makes a really great research advisor like that? Or even a great researcher?

**Jacob Steinhardt:**
I haven't experienced this directly, but I think someone who really comes to mind is exemplifying another important skillset is Peter Abele. Who's just very good at putting processes in place to make his lab run well, creating good processes for students to learn from other students, I think is very valuable. Some people might call that laziness, but I don't think that's really true. students come much more from each other than they can possibly learn from their advisor, just because students have more bandwidth and also it's more of a peer interaction, so you can more authentic interactions, but I think it doesn't happen by default you need to put systems in place. And I think of all labs I've seen, they just have the most systems and really have a lot built up, but I've been thinking a lot about how to get there. I think I've been slowly putting systems in place, but it's somehow a lot of work. And the real thing you want is like meta systems to get other people to help you build the system figured out how to do, but I feel he's figured out somehow.

**Josh Albrecht:**
Yeah. That does seem pretty powerful and pretty useful. Do you have any thoughts on what makes a researcher great?

**Jacob Steinhardt:**
One aspect is longevity. I think there is a lot of researchers who are really good at one thing, but either don't have a diverse enough skillset or just never remake themselves. And so there'll be really relevant for five years or 10 years, but they'll fade. I think there's others who have managed to be really relevant for a long time. And I think at least that kind of the faculty or research lead level. My sense is that what goes into that is investigating a lot of things that have long-term payoffs. So reading in new areas very broadly, just also setting aside time to think everyday or at least every week or deeply, and not just being reactive. I think if you don't do this, you'll be fine for awhile, but eventually you're just going to fade in relevance or not come up with good new ideas. But I think it takes a lot of discipline to do this.

**Jacob Steinhardt:**
I think I'm decently successful at doing, but it really is quite hard and requires a lot of defensiveness around that time. I think the other is also about long-term stuff. You need to think about what you want your lab to be working on a year from now. That requires building up intuition in new areas that can take awhile. If you don't think ahead, then again, you're stuck with whatever people currently have access to. And I think maybe most people don't realize that it can actually take a year or more of intuition building before you're really ready to go in an area. So either as an individual researcher where we actually consistently laying that groundwork or as a research lead, creating that environment where your students lay that groundwork, I think is pretty important and something I didn't appreciate until after I became a professor.

**Kanjun Qiu:**
Interesting. It's not something that you think about as a student before you become a professor.

**Jacob Steinhardt:**
Yeah, I think I didn't realize how much of that was being done for me.

**Kanjun Qiu:**
Yeah. Cool. Awesome. Well thanks Josh for taking the time. This was super interesting.

**Kanjun Qiu:**
Thank you for listening to Generally Intelligent. We love feedback and questions. So please feel free to ping us on Twitter @kanjun and @joshalbrecht or email us with any ideas or corrections. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify for your favorite podcast app. Thanks very much. And we'll see you next time.

<br>

*Thanks to <a href="https://twitter.com/lukelivesfree">Luke Cheng </a> for writing drafts of this post and <a href="https://www.linkedin.com/in/tessajhall/">Tessa Hall</a> for editing the podcast.*
