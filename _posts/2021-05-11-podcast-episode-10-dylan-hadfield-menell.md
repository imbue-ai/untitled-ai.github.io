---
layout: post
title:  "Generally Intelligent #10: Dylan Hadfield-Menell, UC Berkeley/MIT, on the value alignment problem in AI"
date:   2021-05-11 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe src="https://anchor.fm/untitled-ai/embed/episodes/Episode-10-Dylan-Hadfield-Menell--UC-BerkeleyMIT--on-the-value-alignment-problem-in-AI-e10njja" width="100%" frameborder="0" scrolling="no"></iframe>

<br>

Dylan Hadfield-Menell [(Google Scholar)](https://scholar.google.com/citations?user=4mVPFQ8AAAAJ&hl=en) [(Website)](https://engineering.mit.edu/faculty/dylan-hadfield-menell/) recently finished his PhD at UC Berkeley and is starting as an assistant professor at MIT. He works on the problem of designing AI algorithms that pursue the intended goal of their users, designers, and society in general.  This is known as the value alignment problem.

His most recent paper at NeurIPS is [Consequences of Misaligned AI](https://arxiv.org/abs/2102.03896).  It models the value alignment problem in AI by looking at a common situation, where the user’s true goals are only expressed to an AI system through proxies. This initially leads to positive utility, but decreases to negative utility over time as the AI system over-optimizes for the proxy objective.  Their solution is to give the user the ability to update their proxied goals, thus increasing utility again.  This model offers a general look at the consequences of misalignment and how AI recommender systems can be improved.

Dylan would love to hear any questions or comments on his paper, so feel free to reach out!

**Highlights from our conversation:**

👨‍👩‍👧‍👦 How to align AI to human values 

📉 Consequences of misaligned AI -> bias & misdirected optimization

📱 Better AI recommender systems

<br>
*Below are the show notes and full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
<!--more-->
<br />

### Some quotes we loved
> **[3:30] Dylan’s work on normative information about AI systems:**
> “Since then, my research has been, how to provide normative information about AI system behavior. We often talk about, in the world, the distinction between objective and subjective properties. Like predicting images from pixel to pixel is a fairly objective thing. There's a clear well-defined right answer. You predict the right pixels or you don't.  For normative properties of the world. That's not true. 
> 
> When the right answer is not externally defined, you have to appeal to who built the system and what do they want it to do, in order to really answer that question.   And I think most of my research is about trying to understand what are the channels by which we communicate that information. How do we make sure that system's behavior aligns well enough with this subjective goal that we have.”
> 
> 
> **[18:25] The main result in Dylan’s 2020 NeurIPS paper:**
> “What we show is in this model, if you optimize for any fixed proxy utility function, eventually the overall utility is driven either towards a minimum at certain features or overall drives away unbounded if you don’t hit any environmental bounds.
> …
> 
> (Their solution:) We have a property of a proxy utility function and a true utility function such that local improvements in one lead to improvements in the other.  And this implies that if you can update the features and your utility function fast enough, you can use proxy utility functions to maybe not define what you want in the long run, but to provide local directions of improvement for how your system should allocate its effort. And so this is another style of solution.”
> 
> **[31:33] Obvious discoveries:** 
> “I think that is the ultimate dream as a researcher: things that you didn't realize before, but then seem so obvious, you can't imagine not thinking of them in hindsight.  If I can have a couple ideas like that in my career, I will call it a big success.”
> 
> **[33:22] Current AI systems as an analog to compilers:**
> “I've come to believe that a lot of ML as we study it right now will fill a role in the future that's analogous to what compilers fill in AI systems today. 
> …
> Over the course of a long period of time is the combination of decision theory and statistics to effectively build a compiler that allows us to represent now more intelligent behaviors. Really just behaviors defined on complex open-world inputs in a higher level representation that can then be compiled down. That higher level representation in the form of supervised learning is a label dataset. 
> …
> It's a representation of an objective. It's a ranking of different possible behaviors where those behaviors are encoded as the weights of the neural net, the parameters of a policy, something of that nature.  We do have something like the general purpose programming language today. I think the supervised learning data set like Imagenet is, in this analogy, it looks like Python or C or something like that." 

<br>

### Show Notes
* How did Dylan’s research interests start and evolve? [02:00]
* Dylan’s current research interests on normative information about AI system behavior  [03:00]
* Framing AI safety as the principal agent problem from economics [07:51]
* Different approaches to AI safety [08:21]
* How Dylan’s research relates to social media and content recommendation [09:31]
* Language models and their pitfalls in data collection [12:06]
* One solution to the problem: paying for data [14:20]
* Dylan’s NeurIPS 2020 paper, Consequences of Misaligned AI [15:33]
* CEO pay as an analog for AI systems optimization [16:04]
* Dylan’s proposed solutions to over-optimization in his paper [25:04]
* Why their solution lines up well with deployed AI systems in practice [27:07]
* How does clickbait happen? [28:14]
* Managing personal optimization in life [30:36]
* Finding obvious phenomena as a researcher [31:23]
* Current AI systems as an analog to compilers [33:22]
* Creating datasets to allow “general purpose programming” to happen in AI, rather than “low-level code” [36:00]
* Dylan’s paper on social norms: Silly rules improve the capacity of agents to learn stable enforcement and compliance behaviors  [41:49]
* Dylan’s “controversial” opinions for ML - choosing the wrong ways to fix biased datasets [47:36]
* How to better teach ML systems design in academia [52:07]
* Weakly supervised learning for general purpose ML programming [55:30]
* Dylan’s concerns with current AI systems - shallow metrics and negative externalities [57:44] 
* The importance of subjectivity in AI and normative information [58:56]
* Enabling better content recommendation and filters for users [1:04:11]
* Do more choices lead to user happiness? [1:08:16]
* Creating your own information diet [1:13:19]
* Lack of power and feedback for users in content recommendation [1:14:48]
* Problems with unsupervised learning regarding AI safety [1:19:41]
* Mathematical models to measure manipulation [1:22:18]
* Work that has impacted Dylan most [1:25:58]
* Dylan’s request for the audience [1:30:24]

<br>

### Transcript
**Dylan Hadfield-Menell:**
Since then, my research has been how to provide normative information about AI system behavior. We often talk about in the world, the distinction between objective and subjective properties, like predicting images from pixel to pixel is a fairly objective thing. And there's a clear well-defined right answer. You predict the right pixels or you don't. For normative properties of the world, that's not true. When the right answer is not externally defined, you have to appeal to who built the system and what do they want it to do in order to really answer that question. And I think most of my research is about trying to understand what are the channels by which we communicate that information, how do we make sure that system's behavior aligns well enough with the subjective goal at hand?

**Kanjun Qiu:**
Hey, everyone, I'm Kanjun Qiu. And this is Josh Albrecht. We run Untitled AI, an independent research lab that's investigating the fundamentals of learning across both humans and machines in order to create more general machine intelligence. And this is Generally Intelligent, a series of conversations with deep learning researchers about their behind-the-scenes ideas, opinions, and intuitions that they normally wouldn't have the space to share in a typical paper or doc. We made this podcast for other researchers. We hope this ultimately becomes a sort of global colloquium where we can get inspiration from each other. And where guest speakers are available to everyone, not just people inside their own lab.

**Kanjun Qiu:**
Dylan Hadfield-Menell did his PhD at Berkeley with Peter Abele, Stuart Russell, and Anca Dragan. He's focused on the value alignment problem in AI in order to design algorithms that learn to pursue the intended goal of their users and their designers and of society in general.

**Kanjun Qiu:**
So you went to Berkeley and did your PhD. How did you develop your current interest areas? How did you get to here?

**Dylan Hadfield-Menell:**
A little bit haphazardly. I was working on a problem called integrated task and motion planning when I started my PhD. I'm not sure how interesting it is to go into the details of that. It's a very interesting research problem to the extent that people are interested in neuro-symbolic things these days. It's roughly the problem of combining symbolic planning over tasks. So, "Pick up this cup, move to the dining room. Pick up that plate, put it down in the dishwasher," with the concrete realization of that as a motion. You have to actually control a robot arm. And that involves ultimately providing a sequence of voltages at some frequency. Doing that in a way that doesn't cause the arm to run into things is challenging on its own.

**Dylan Hadfield-Menell:**
So I've worked on systems that integrated those two things and worked at combining this type of continuous and discrete reasoning. That was my primary goal for the first year or two years or so of PhD. About one year or so into my PhD, one of my advisors, Stuart Russell, came back from a sabbatical, which he'd been thinking about a bunch of things, but including them was AI safety. So this idea that controlling AI systems was a real serious challenge to the types of paradigm that he had looked at and a lot of the ways that AI systems are built. He and I talked about that for about a year, started discussing potential areas to explore. And about a year in is when I made the decision to jump in and adopt that as my primary research area.

**Dylan Hadfield-Menell:**
Since then, my research has been, we've called it a bunch of different things. For me, the most accurate way to describe it is figuring out how to provide normative information about AI system behavior. We often talk about in the world, the distinction between objective and subjective properties. I think one of the large biases that the AI field has is towards objectification in the sense that we treat the world as an objective process that exists and continues and data allows us to observe and predict this process. To be sure there is an incredible amount of that at play in many AI applications. In some ways how far down the intelligent stack you are, kind of deals with some of these things. Like predicting images from pixel to pixel is a fairly objective thing.

**Dylan Hadfield-Menell:**
Now, the background distribution that you bring to play in filling in details might be not quite as objective, or it could be very dependent on the experience that you've had as well. But that problem, there's a clear well-defined right answer. You predict the right pixels or you don't. We could disagree on the ways to measure error, but we're going to agree on the correct answer sense.

**Dylan Hadfield-Menell:**
For normative properties of the world, that's not true. So let's say you're now a system that is influencing some aspects of the world and that changes which pixels you're going to see. We can define the problem of predicting, "If I do X, how will the pixels change?" And so the pixels could go to the left or to the right. Is it good for the pixels to go to the left or the right is a different type of question. The right answer is not externally defined in some. You have to appeal to, "Well, who built the system and what do they want it to do in order to really answer that question?" And I think most of my research is about trying to understand what are the channels by which we communicate that information, how do we make sure that system is behavior aligns well enough with this subjective goal that we have.

**Kanjun Qiu:**
Got it. How did you end up in this? Different people have different approaches to this idea of building AI that is compatible with humans. And did you feel like this idea of subjective versus objective goals is the most important after evaluating a whole bunch of different kind of ways to think about how to build something that's compatible? Or was it obvious that this is the primary thing? Or how did you get here?

**Dylan Hadfield-Menell:**
I think the initial framing of the problem for me was always about, what's the correct objective? When I started working on this problem, I definitely did not have access to the sentences I just said. I think it's very true though. A big part of what's happened in this research is coming up with the right terminology to communicate these concepts. I think in AI and machine learning, we've been very focused on building proof of concepts. For a very long time, as it's been like, "Can we build something intelligent?" And intelligent was pretty broadly interpreted. Could we build proof of concepts of intelligence? And that's a nature of what papers look like. Now we have several of those proofs of concepts about what's possible. Then you have to start thinking about the difference between what's possible and how much can you achieve those possibilities in practical settings and in the right ways.

**Dylan Hadfield-Menell:**
My background comes from a planning robotics context. So to me, I think most AI applications can be thought of as some version of a Markov decision process. That's not really true, but that's my default way of looking at it. So when I think about these objective versus subjective properties of the world, in a Markov decision process, they're very clearly delineated into objective properties of the world or properties of a state transition matrix. Conditioned on your actions, that's an observable fact.

**Dylan Hadfield-Menell:**
Alternatively, the objective in that case, which is a confusing term in this analogy, the reward function provides the subjective information, the normative information that tells you right from wrong. A lot of my thinking on this was influenced by a course I took in my senior year, which just happened to be quite related, which is called the Economics of Incentives. But it was done to finish out a concentration in Econ. And that course dealt with economics study of the principal agent problem. And so my initial framing of this has basically been that this is a principal agent problem in artificial intelligence effectively.

**Kanjun Qiu:**
That's really interesting. I actually don't know much about the field of safety or whatever this field is. Do you find that other people also characterize it as a principal agent problem or that there are a lot of really different characterizations?

**Josh Albrecht:**
Or would you still characterize it?

**Kanjun Qiu:**
Is there a disagreement? Yeah. Would you still characterize it this way?

**Dylan Hadfield-Menell:**
I think there are interesting principle agent problems to be studied in AI alignment or in this space. I don't think everyone necessarily views it that way. I'm not sure everyone would use that terminology. I think most people would say that's an interesting formalization of the problem. I think many people are interested in ways that the breakdown between an agent and its environment is violated in a deployment, opportunities for our system to impact itself or ways in which the theory doesn't account for that, I think is another strand.

**Dylan Hadfield-Menell:**
I think to my end, I'm interested in thinking about it as a type of principal agent problem combined with really a communication problem. There's a question about how much bandwidth can you get about what's right and wrong and how can you provide that information in a meaningful way? I think a lot about social media systems and content recommendation in that space.

**Dylan Hadfield-Menell:**
So in this case, you have a platform which has a lot of different content and your goal is to rank that and show it to different people. And this could be ranking videos on a site like YouTube, it could be ranking posts or links to articles from friends on something like Facebook, could be ranking different group recommendations or suggestions that you might see. A lot of how this has done is based off of behavioral data currently. What do people who've looked at things like the things you've looked at ... yeah, it's looking for patterns in behavior. And in effect, this is grouping people into categories based off of patterns of behavior, and then using that to show people different content.

**Dylan Hadfield-Menell:**
So the question of predicting behavior based on past behavior and using other people as examples, in effect, that makes a lot of sense. In a way that's an objective problem. And there's huge bandwidth about that problem in the sense that you have, if you're a large platform, I don't know what the right number of interactions you'd have per day would be, but it's huge. You have a ton of data. Like if you think about that, it's like a fire hose jacked into what people are going to do. You're using that to reinforce certain aspects of behavior.

**Dylan Hadfield-Menell:**
And the question is, which things should you reinforce? You can say, "If I show people this, they will click on it. Is that a good thing or a bad thing?" Who's asking is the really important question there. Even putting that aside, I think even if you're selfishly YouTubing, and all you care about is YouTube's wellbeing, it's hard to answer that question. Once you get into questions of PR liability for recommending a particular video, "Is this a good idea or bad idea?" I imagine there's a lot of fine grain detail you'd like to take advantage of, but that's just not currently there in the system. And part of it is because there is simply not as much normative data in the system, from my perspective.

**Dylan Hadfield-Menell:**
There's billions of decisions that go into the behavior prediction model, but potentially in this case, if it's just show people the things that they're likely to click on, which is not what's happening now, that's like version one of these types of recommender systems. That's one decision going into that compared to billions of decisions being used to predict what will happen in the world. In turn, it doesn't matter how hard you think about that one choice. There's only so much information in it. It can only limit what your system's going to do in practice.

**Dylan Hadfield-Menell:**
There's a tweet from Alex Hannah, I think from the Google Ethics ML team that summed up some of this in language models fairly well where it was talking about an example with their data collection method, where they had excluded ... like it was like related to sex or gender. And you could understand why that would be excluded, but also at the same time, why that might blind a language model to important properties of the world, or that choice might have large impacts in the biases present in the training data for that model.

**Dylan Hadfield-Menell:**
What she said was that even if your language model has billions of parameters, there are  hundreds of decisions that go into selecting that data. When I think about it, that is actually the core tension in really successfully deploying AI systems. I think that a lot of the ways in which systems are brittle and they don't work is because we have all of these different problems that are cropping up, that we rely on ML researchers or practitioners to fix.

**Dylan Hadfield-Menell:**
The people who've been doing ML work are really smart people who are really good at pattern matching and this like black art of connecting this loop of system behavior back to changes in training data or training algorithm or something like that and making that whole loop work. I think we've made a choice to say that AI is the machine part of that loop, which I think is fine. And if you want a proof of concept, then it's useful to do things like this in the world. Like the machine component to that loop is important. Smart people are going to do smart people things. You don't want to get misled by tricks there or something.

**Dylan Hadfield-Menell:**
But now that we've proved that component is valuable, I think you should really be studying this interaction loop of system behavior, system designer, and some sort of actual feedback mechanism and how that works almost as a control system of itself. And you can think about that at a binary point of one person, one system. You can think about that as an organization managing an AI deployment. And you can also think about that as a large multi-stakeholder interaction on like an internet platform.

**Josh Albrecht:**
So, what are some ways out of that quandary of they've got billions of parameters and you make 10 decisions about what words to include or not, and you're like, "All right, great. Ship it." We don't have time to make billions of decisions about this as a researcher, right? But obviously there are other ways we can do this. So what are some other ways to escape this?

**Dylan Hadfield-Menell:**
I think part of the answer is we should realize that data is valuable and pay for it. I think there is a sense in which there's lots of data around that's not exactly the right thing. And you can invest in technologies to more effectively curate that data. You can invest in systems to more effectively go and get that data and get it from people.

**Dylan Hadfield-Menell:**
My fear is that you can get really far and make a lot of money based off of free data. I think if you want to provide real value to people, you need to invest in building better signals of what they value. And that includes building bigger measurement systems for complex parts of the world and figuring out how to incorporate that into objectives. This is where things start to build up against my NeurIPS paper and why I'm excited about the results in there.

**Kanjun Qiu:**
Why don't we dive into that because it's a very natural ...

**Dylan Hadfield-Menell:**
Sure. So the paper took a very direct approach to basically looking at an AI system and a system designer as a principal agent interaction. And so when I say that, what I mean is that you have a principal, which is an actor that has a utility function and objective that they're trying to maximize in some way through actions in the world. And then you have an agent who has to act on their behalf. And the restriction between these agents, the way that the principal gets the agent to do what they want is to pay them. In economics, this is meant to set up how you get people to make like different goods or something like that, where you pay them for each individual item they produce. And if to pay them across a bunch of different items, they'll allocate their effort in smart ways. And that's what this research field studies.

**Dylan Hadfield-Menell:**
One of the big outcomes of this was the decision by companies to have large degrees of stock packages in CEO compensation, which is something that we can come back to a little bit later on, because I think it relates to the conclusion of the paper. So we're looking at this, we've got a system designer, they have a utility function and they have an agent which is going to optimize for a different utility function. We'll call this the proxy utility function. The goal here is we're trying to mimic part of the setup of how AI systems are deployed today. The utility function that you actually care about is maybe the classification function you really want your system to implement. The proxy you identify is the empirical datasets with labels that represents a proxy you'd like your system to optimize. It could be a measurement in the world in your ecosystem that your recommender system tries to minimize.

**Dylan Hadfield-Menell:**
Our goal in this work is to look at what happens when you're not able to perfectly describe your values to the system. The way that we operationalize this is that you can only give a reward function on a subset of the features you care about. So your utility function operates on a set of features of the world. Based off the assumptions we make, you can think of these like goods or attributes. So these are things where if these features go up, utility goes up. And your utility can be a loosely thought of as a sum of functions defined on these individual features. The AI system is only going to know about a subset of these features and is going to work to optimize that.

**Dylan Hadfield-Menell:**
The final aspect of what we have is a resource constraint. And this means that you can't drive all of the features to positive infinity altogether. Altogether, this represents a set of assumptions that captures a utility model. I won't argue that it's necessarily true and the best thing in the world. Many of the assumptions that we make are in line with the standard type of assumptions that economists make about utility functions. What we show is in this model, if you optimize for any fixed proxy utility function, eventually the overall utility is driven either towards a minimum at certain features or overall drives away unbounded if you don't hit any environmental bounds.

**Josh Albrecht:**
Very bad outcome.

**Dylan Hadfield-Menell:**
Yes. And you can understand intuitively what happens. You have these two clear phases of the optimization. One where you're on the interior, you're at the initial point and the world is just relatively un-optimized. And so the optimizer can take features or resources that are allocated between the different features inside of the utility function and reallocate them easily and gather unused resources and push them into the things that you care about. And this is really good. So if you have zero optimization on your system and you add a little bit of optimization, it probably doesn't even matter that you have the perfect objective in a lot of ways, because you'll get more efficient use of unutilized resources. And that produces value.

**Dylan Hadfield-Menell:**
What happens is as systems get more optimized, you start to hit the resource bounds on the overall set. And then the behavior becomes something quite different. Rather than efficiently reallocating things between what you're referencing, you start to take resources from unreferenced features or attributes of the world and reallocate those towards your features. And because we assume things like diminishing marginal returns, eventually this gets outweighed.

**Dylan Hadfield-Menell:**
And so what this says is if you're optimizing and using measurements of the world to drive behavior in this kind of optimizing fashion, you need to be very careful about which of these regimes you're in and how you manage the incentives of your systems. And just as much as you want to think about getting those incentives up and running and making use of them early on, you want to think about how you blunt them on the other end and how you prevent them from going into a runaway setting.

**Dylan Hadfield-Menell:**
That's why our headline result, which is this large negative result about your ability to optimize for proxy objectives in the face of shared resources and diminishing marginal returns. If you don't have diminishing marginal returns, then perhaps you're okay with doing this big reallocation. I still think you'd want to understand what you're doing better, but that's our primary result.

**Dylan Hadfield-Menell:**
This applies to optimizing agents, right? This theory. And it's intended for AI systems. I think it can describe some of the ways that AI systems' optimizing engagement were really useful early on, have become less useful over time. But I also think if we go back and think about that CEO pay example. This is an example where there's a feature of the world that they were able to tie very tightly to the incentives of these very powerful people, which was stock prices.

**Dylan Hadfield-Menell:**
Early on when this was done, it was because there was actually an issue with CEOs not paying enough attention to stock price, caring about their own things. And we could argue whether that was better or worse than what we have now, but that was the reason why they switched to these types of compensation packages. I think you can look at some of the externalities in the world of the stock market in a way, as a consequence of these types of results.

**Kanjun Qiu:**
It's really interesting.

**Josh Albrecht:**
Around what year did people start switching?

**Dylan Hadfield-Menell:**
The '80s were a large part of when this shift in CEO pay was driven to a big degree, as far as I know. And I think it's increased since then in several ways due to the fact that it kind of worked. Incentives are very hard ... Well, it's still working from the standpoint of shareholders. The stock market is still doing quite well.

**Josh Albrecht:**
Yeah. In fact, one can say that it's almost working a little too well in that all the stocks are going very up and to the right. Everyone's doing a great job on that particular metric.

**Kanjun Qiu:**
So now, knowing, seeing what is happening with CEO and the stock market taking this concrete example and having done this research, what would you change about the current situation?

**Dylan Hadfield-Menell:**
About the stock market? I think that is a hard question.

**Josh Albrecht:**
I was going to ask a similar question, which I also liked from the paper, which I thought there were two parts of the paper. One was the main negative result, but I also really liked the possible solutions.

**Dylan Hadfield-Menell:**
We do have that. And I think that there is something to be said about potentially how you might move in this direction for the stock market. Actually, part of the answer in the stock market is the incorporation of different signals that have started to take meanings. So I think, and this is where I'm definitely outside of my area of expertise. So with that, disclaimer, I think things like ESG as there are these movements around creating different rankings of companies based off of environmental impact and other things. So this is moving towards having a much more diverse set of measurements of companies that can be incorporated. And I think in general, that is a really interesting way to attack the problem. And this is what the paper points towards. We look at two styles of solutions. The first is the textbook solution in a way, which is regularization. I would argue that overfitting is an example of misalignment.

**Dylan Hadfield-Menell:**
Overfitting is an example of misalignment and regularization is an early example of how AI researchers got around. In this case, it's the observation that if you have resources that are prediction resources in terms of classes based off of the features and you're trying to allocate them, if you have a data set that represents that, which is even relatively small, that can be really valuable initially if you optimize to do better than that because doing better at that pushes you to allocate resources towards the right things in some sense. But then as you optimize further and further on those directions, you enter a different regime of the optimization and your performance on the true metric drops off.

**Dylan Hadfield-Menell:**
You can even think about extending the analogy to head loss function, where each dimension is predictive performance on each data point. In which case each feature actually does correspond to the features from our model. And you actually do have missing features. And so, this talks about the limits of perfectly optimizing any data set on a meaningful subset of the overall data. I'm sure there are actual stat amount or results that prove that in much more precise ways. This is just to draw a broad analogy towards the problem.

**Dylan Hadfield-Menell:**
And so, regularization tells us that if you can loosely reference all of the features somehow or pull the optimization back from going through extremes, you can still do relatively well. And so, we analyze a result that says, "If you can measure distance from the unreferenced attributes of the world." So, if you can loosely reference all possible features and include cost functions for changing things too much, then you can do well and reliably produce utility. This is the first result we have. It's not surprising. It passes a gut-check and there's a line of research in AI safety that focuses on impact avoidance, which I view as effectively trying to operationalize this in open world contexts.

**Dylan Hadfield-Menell:**
The other approach that we identify is what we call an interactive solution. And in this case, what we show is that for this model, if you choose the features to include in a particular way, then there's a local neighborhood where you're guaranteed that your utility functions alyn, by alyn increases in the proxy or increases in the overall utility. If I'm was going to say that again, we have a property of a proxy utility function and a true utility function such that locally improvements in one lead to improvements in the other.

**Dylan Hadfield-Menell:**
And this implies that if you can update the features in your utility function fast enough, you can use proxy utility functions to maybe not define what you want in the long run but to provide local directions of improvement for how your system should allocate its effort. And so, this is another style of solution that we explored, which I think aligned somewhat well with the ways that systems are deployed in practice.

**Kanjun Qiu:**
Why is that?

**Dylan Hadfield-Menell:**
When you roll out AI systems in a production setting, you are engaged in this process of supervision and constant updates where you're looking at different metrics, both of the AI system and of the system overall and those are impacting both the systems incentives in the sense that you're using them to change the training data that the model is using. And actually often the human incentives in the sense that the various metrics that those models are being updated towards are involved in the compensation packages of ML engineers or what have you.

**Dylan Hadfield-Menell:**
So, there's this process of iteration and updating. I was involved in a paper that we published at the participatory ML workshop that detailed a few of these updates for recommender systems. There are things like clicks being an early optimization signal that leads to the development of Clickbait. And then there's this interesting study of what actually happened with Clickbait, right? Clickbait was a thing that didn't exist. If you go back to the 1970s and say, Clickbait, no one will understand what you mean.

**Dylan Hadfield-Menell:**
In practice, it was this phenomenon that occurred, which then starts off as this pattern in user behavior, which then the system designers become aware of either directly or indirectly through their use of the system or people reporting or user surveys or something like that. Then you have to invent a concept of Clickbait, which describes all of these different disparate reports that you're getting. And then you have to come up with some way to track it, which in practice, which is the Opera. So, you have to identify this abstract value that matters for your system, where I'm using value really loosely here.

**Dylan Hadfield-Menell:**
It's like an abstract concept of something that's important that's not being appropriately accounted for. And then you have to operationalize that. In this case, that's when they started using Watchtower metrics, which had some of their own externalities. For a news links, it was returned time, which was that proxy for watch time. So, if you clicked on a link and then came back immediately, that's a signal that it's Clickbait. And that can be included to do direct things like in the sense like updating the AI systems objectives. Nowadays, you might recognize this concept and then pay people to collect a dataset of those examples and train a model to then downright that type of content.

**Kanjun Qiu:**
Interesting. Yeah. Now I'm about systems. And one thing I've noticed in products that older is that they often get worse. So, Google is a good example, actually, where SEO was how Google ranks things and Google search results are really great for a long time because it was a good optimization function for what people do more.  But now you get all of these people who are over optimizing for SEO metrics and the performance force. And also life is like this. I think it's maybe midlife crisis is like over-optimization for a single metric that was set when you were 20.

**Dylan Hadfield-Menell:**
I think we spent a lot of time looking at the ways that people pursue goals and less time at the structures whereby people manage their goals and pick them and update them and iterate on them and all of that. I think there's a lot of intelligence in how we manage the optimization component of ourselves and making things work and not having things run away on overdrive.

**Kanjun Qiu:**
Yes.

**Josh Albrecht:**
I really liked the idea. It seems to me simple at its core. Okay. And you make the system and then the answer is just check back in. Is it still doing what you wanted? And the more frequently you can check back in relative to how fast it can optimize the world, the better you are in a sense for optimizing your true utility function, right?

**Dylan Hadfield-Menell:**
Mm-hmm (affirmative). You always have to worry about things like that being the result of your research because if it's so obvious then have you done anything useful and why haven't other people done it yet? I think that is the ultimate dream as a researcher is things that you didn't realize before but then seem so obvious you can't imagine not thinking of them in hindsight. Yeah. If I can have a couple ideas like that in my career, I will call it a big success. In this case, the big thing that we're applying and it makes me think there might be a useful insight here is the AI field has been working on building prototypes for a long time in a very real sense.

**Dylan Hadfield-Menell:**
And there is a question of if intelligence isn't this objective thing, if it's not just there, isn't a right answer and it's like, "Oh, but clearly then what does it mean and how do we engage with that and how does that change the way we build our models is I think a fairly deep shift, in some sense?" It relates to what we often think we're trying to do with AI systems. I often think a lot about my first ML course where you walk in and I very clearly remember this because my advisor Leslie was teaching it. And I remember the first thing we did was like, "Okay. So, supervised learning."

**Dylan Hadfield-Menell:**
It's defined by a dataset, a hypothesis class an input space, output space, a set of labels and things like that, right? Those just are the boundaries of the problem that we studied. That's really important. But in reality, data sets are a way for us to encode desired goals. And the machine learning itself is how to operationalize that in coding. While you can't operationalize anything, figuring out how to operationalize stuff is good but these benchmark data sets are going to be equivalent to benchmark code snippets to test like ramp.

**Dylan Hadfield-Menell:**
That's not what real code looks like. It's much more complex. I've come to believe that a lot of ML as we study it right now, will fill a role in the future that's analogous to what compilers fill in AI systems today. I have a story about artificial intelligence, which is that we just got here because we realized we could program computers and I was cool and they could do things that seemed cool.

**Dylan Hadfield-Menell:**
And then we looked at intelligence and people and that's this whole mysterious thing. And we wondered, "Okay. Can we program systems to do those types of intelligent things?" Which is a perfectly natural thing to do. As usual, we've underestimated intelligence in lots of ways. The first answer was basically no. If you think about the attempts that were very direct attempts to program input, output routines in general purpose programming languages, a lot of early NLP looks that way, a lot of early planning looks this way.

**Dylan Hadfield-Menell:**
A lot of approaches were very focused on directly encoding behavior down to the point where I did my undergrad, I graduated in 2012. And as part of that, in my early coursework did a visual survey as a routine for a robot, which is one of the simplest control techniques you could do. I mean, it involves hand coding, blob detection based on pixels, where you wrote a program that went through pixel by pixel and had a dynamic programming relationship for counting up the number of red pixels nearby and using this to track centroids of red pixels.

**Dylan Hadfield-Menell:**
This is not brand new at this point in time but this wasn't a crazy thing to have done. And for several robotics tasks, this was probably the best thing you could find. There's just like the classic simple thing that we can't beat with anything else. Okay. So, through this process, we learned that is really hard. Most of the behaviors you could write down or programs you could write down that depend on real world input, just do dumb things. I think that is a rough analogy to when computers were invented in the early days and code was written in machine code or assembly where you had to do all of these extra things, you have to manage memory.

**Dylan Hadfield-Menell:**
And it was this very integrated thing, largely because we were working on prototypes. I mean, we're doing useful things with it to be sure but we were limited by our programming tools, right? The complexity of an individual program or a team of programmers to manage large code bases in assembly it was just, oh my goodness. So, what's a huge thing that happened. We invented compilers, right? We invented general purpose programming languages and techniques to take those loose non-executable representations of machine behavior and compile them into executable representations that we can run on computers.

**Dylan Hadfield-Menell:**
And then we developed an entire discipline on top of that of software engineering to manage all the complexities that only exist once we get to that general purpose programming life. It's like we can we can't do software engineering until we have that representation and compiler I think. You can see where I'm heading with this when we think about AI systems. We tried directly programming them in low level code and we discovered that that wasn't really doable with some interesting proof of concepts like Rodney Brooks' assumption architecture is one of the best examples of how far you can push this paradigm if you're just a good engineer.

**Dylan Hadfield-Menell:**
But then what happened over the course of a long period of time is the combination of decision theory and statistics to effectively build a compiler that allows us to represent now more intelligent behavior is really just behaviors defined on complex open-world inputs in a higher level representation that can then be compiled down. That higher level representation in the form of supervised learning is a labeled dataset. That executable representation is say conflict or nowadays it might be a transformer. And the actual linkage that goes from one to the other is the machine learning optimization code.

**Josh Albrecht:**
Interesting. I really like this. I now I understand what you're saying earlier when you were saying like, "Oh, the machine learning that we're doing today is prototypes." We're building prototypes. This is what you want.

**Dylan Hadfield-Menell:**
We're a discipline of how do you optimize objectives? What should those objectives be? Is a whole new field is analogous.

**Josh Albrecht:**
How do we create those objectives? How do I manage those objectives? And specifically in the current iteration that looks like, how do we create supervise learning data sets? How do we manage the effective qualitative objectives that are represented within those data sets? We talk about computer vision as being solved in air quotes. I think we've made incredible progress on it but a lot of that progress is simply from the fact that we have image net as our thing. It's a combination of we built a compiler that can actually compile a interesting enough visual program into an executable efficiently executable representation. That's huge. But a huge component of the investment is in creating that image in that dataset.

**Dylan Hadfield-Menell:**
Yes. I think actually that this point is definitely undervalued by a lot of people who work in the field that the dataset and if you look at the data that exist today, image net CFR and this et cetera, what goals are those reflecting? And is that going to get us to something that really understands the world at a much deeper level? And an interesting question and from our perspective in a search, no.

**Josh Albrecht:**
I think that's right. And certainly mine as well.

**Dylan Hadfield-Menell:**
So, what's needed to construct a new dataset that actually gets you there.

**Josh Albrecht:**
Yes. Oh, just on this topic, there's a paper by a baby bear honey, I think is her name but it's called large image data sets of Pyrrhic victory for computer vision. It looks at the creation of a lot of these datasets and identifies some problematic components. I think there's a data set of like 80 million of very small thumbnail size images, which have been scraped from Google image search using a repository of knowledge. I think it goes from psych to generating a bunch of words from that.

**Josh Albrecht:**
And then when it comes to image search, scraping the results, putting that into a dataset, several of the categories use are quite offensive, including I think the N word may have been one of them. There's this aspect we talked about, how many decisions do you have going into data? Well, there's a decision of we're going to use this bank of words and that source of images and piece the two together and that will be our data. And so, you can get a lot of information about the world from that but there's very little normative choice going into that.

**Kanjun Qiu:**
Interesting. Yeah. I think about the analog to human intelligence in the real world, analog of datasets, the analog is the culture we grow up in and the norms and values we're surrounded by in some sense that shows our beliefs and how we behave and all of those things.

**Josh Albrecht:**
I would say a data set can represent a lot of things. It's like a programming language in that sense from this analogy. And to the extent that data sets can encode what happens when you search things on Google that I think no one would disagree with that data set being a good representation of what that looked like at a particular point in time at least. I think what you're pointing out is that there are these values and norms that are embedded in our culture, which are a big part of our behavior, which aren't currently represented within datasets or are well-represented within our data in a good way, is that.

**Kanjun Qiu:**
Maybe. Although I don't know if that is exactly what I was saying a little bit. Okay. If datasets are a way to encode our desired goals, people in a culture in code a certain desired goals and humans as these machine learning models in our heads, what we're intaking data day in and day out is this data set of the other people around us, their behaviors, their expectations and the culture around us. And so, in some sense in the same way that data sets up encoding goals and actually really determined that model we get out. It's also true of our surroundings.

**Josh Albrecht:**
On that note of the culture thing, I think you had another paper a silly rules to prove the capacity of agents alone, stable enforcement and compliance and behaviors, which I thought was just a interesting idea. That's pretty related to that.

**Dylan Hadfield-Menell:**
Yes. I think when you start to talk about this normative data, there's a question of where does it come from and how can you learn about it? And I think some people disagree with this but largely speaking, there are two types of answers that people talk about. One is top down and the other is bottom up. And so, top down comes from the idea of you figure out the right ideas, you figure out the right ethics and you build that into your system from the top-down. And bottom up involves more of learning from human behavior.

**Dylan Hadfield-Menell:**
People often try to stroll this approach as learning, assuming that human behavior is moral and building that into your system, which I think is not necessarily true. I think you can observe more about the world than what people do directly from that standpoint. So, for me, one aspect of human behavior that I think is important and that the silly rules for work plays into is a phenomenon of collective enforcement of norms.

**Dylan Hadfield-Menell:**
We're in a group. And if I started saying mean things to one of you, the other one would probably stand up and defend them and to come after me. And from a purely selfish perspective, this doesn't really make sense but as people, it really makes sense. I think what's interesting is probably if one of you started going after me, the same is probably also true, even though you two are your colleagues, you work together and it was a whole bunch of things but you would still jump to this defensive. This is an example of collective enforcement.

**Dylan Hadfield-Menell:**
There's one action being taken and someone's choosing to enforce a norm at a small but still a cost to themselves. And why this happens is real puzzle for people who use game theory and individual motivation to explain human behavior. I'm less interested in that. I think it does happen. I think it's very interesting as an example of how we as a group communicate on what's okay and what's not okay. The question of what will this group of people choose to punish is I think a really important type of cultural fluency that you need to have to interact in groups effectively.

**Dylan Hadfield-Menell:**
This is like reading the room basically but what type of dress is allowed, what types of words are allowed, who gets to talk when, all of these rules apart of how we I think, fit in and make things work as we can interpret these contexts well. Building AI systems that are able to make that prediction, whether a group will punish something as an objective property of the world. So, I think learning to predict that as an example of bottom up ethics and integrating that into an AI system seems like something that would enable it to interact in more settings more effectively.

**Dylan Hadfield-Menell:**
Now, I think how you would apply that to large digital settings is a very interesting perspective. In particular, singling people out and kicking them out of the group is an old thing that we've done to enforce these types of norms. That's this type of collective enforcement historically in small groups. And you can imagine that's actually a pretty devastating punishment back then. And your odds of survival are very low on your own. If you believe this story of human groups, one of the reasons we invented laws is to manage the scaling problems that come into play from doing this type of collective enforcement in larger groups.

**Dylan Hadfield-Menell:**
And I think one of the things that's interesting with the advent of modern information technologies, things like Twitter is the ability to coordinate collective enforcement of norms on a scale that we haven't been able to before and at a rate we haven't been able to before. I think cancel culture is a really loaded word. So, I don't want to use that but the notion that you can be held responsible for certain types of behaviors by communities in mass. I think a lot of people act as if it's a very new thing and it certainly is related to technology but I actually think it's a reoccurance of a very old thing.

**Dylan Hadfield-Menell:**
I think it's interesting to point out that the groups that have turned to that, which in my mind, I think from this analogy, this is an alternative type of justice system. And the groups that have turned to that are the ones that have been at least from their perspective to service by the current justice system, thinking specifically about women black peoples in those types of me too movement and also other events. That I think is a very interesting framing to think about here that this work brings up for me.

**Kanjun Qiu:**
Interesting. A collective enforcement as an alternative to commit new laws.

**Dylan Hadfield-Menell:**
I think there's a question of how complicated are the norms you're trying to enforce. Do you look at it as a justice system? There are things that would certainly be better or worse like aspects to it. But to me, at least when you frame it that way, the notion that there are innocence that are harmed as a result of it is expected but certainly not something that means it's bad overall. It actually provides a pretty clear baseline within the United States of what you could compare it to. I think we looked at people in essence harmed by the American justice system versus harmed by online grouping or exclusions. I think it's probably pretty stark.

**Kanjun Qiu:**
That's a really interesting perspective

**Josh Albrecht:**
On this topic of controversial opinions maybe, are there any controversial opinions that you have maybe more on the MLS type?

**Dylan Hadfield-Menell:**
Yeah. Definitely. I think one of the big outcomes of my work, which we've talked about a bit earlier is this split between objective and subjective and how we choose to make those splits and how that impacts what type of work we do and what we choose to invest in. I think that our fields chooses to focus on the wrong things here.

**Dylan Hadfield-Menell:**
... chooses to focus on the wrong things here almost directly. One example that we use in ML systems is bias in hiring. And people are sort of surprised by the fact that this bias exists, or what are we going to do about it? We've got this bias data. What options do we have? It's amazing that we haven't stopped to think very much, "Why would you expect this data to be unbiased?"

**Kanjun Qiu:**
Mm-hmm (affirmative).

**Dylan Hadfield-Menell:**
And why would you expect this data that you were able to collect for free to represent the hiring of your objectives of your company today? If you think specifically about a company that's been around for 20 years that has a large set of resumes to use to train their models, is your HR strategy today the same as it was 20 years ago? No, absolutely not, in lots of ways. So why would you expect the data from them to be useful for your hiring now?

**Dylan Hadfield-Menell:**
Maybe in really loose ways, you could expect that to be good, but it's not as though predicting who's going to get good performance reviews three years down the road is actually a metric anyone cares about, and yet you have conversations with people at conferences all the time about this fairness, accuracy trade off. And it's not real.

**Kanjun Qiu:**
Yeah.

**Dylan Hadfield-Menell:**
You have a specification for the behavior that your system is supposed to exhibit. Your metrics or tools to get to that behavior. And if people are telling you, "You're not exhibiting the correct behavior," that's not a performance accuracy trade off, that's just your system doesn't meet it's spec.

**Kanjun Qiu:**
I really like it.

**Dylan Hadfield-Menell:**
If you take the perspective that these are expressions of desired behaviors, a lot of other things change in how you approach these problems?

**Kanjun Qiu:**
Yeah, that's totally true.

**Dylan Hadfield-Menell:**
I think the default textbook answer for how do you do this hiring, filtering process is you would take five recruiters from your team who were filtering resumes, you give them a tool that allows them to filter resumes and generate training data, and perhaps some tools that allow them to filter old resumes as a way to bootstrap. And maybe you have some of these existing signals. You can do weak labeling functions. I'm really interested in work that does weekly supervised learning. I think that's a very important and interesting direction to explore, where you're looking at leveraging the ability for a person to create a lot of normative decisions that go into what a system is going to do, and have a lot of control over the final behavior of the system.

**Dylan Hadfield-Menell:**
The default textbook solution to a prediction problem should be a business process that involves people solving that problem, it shouldn't just be the manufacturing line. It should also include a story about how people fit into that manufacturing line. And I think AI is this deceptive thing because you are trying to build something that can operate autonomously. And so there is this dividing line that's important to set up what is the system going to do on its own? What are the concerns for the person and the system itself?

**Kanjun Qiu:**
Yeah.

**Dylan Hadfield-Menell:**
But we often take a very maximalist approach to, "The system does everything on its own, and that's what we're interested in." And in part that's driven by the way that our fields measures performance, you have to be able to say, "I'm the researcher. What I did goes off into a corner, and then there's what the system did," and you want to bucket that off. And in practice, we should be just thinking much more about how can we use these tools to build systems that we want, and verify that systems are doing what they want, and manage that deployment, and have good processes to iterate?

**Dylan Hadfield-Menell:**
And I think companies are doing this, right? I want to be clear that I'm not sitting here throwing stones and saying that I don't think this is what we're doing in a way. I think if you have a system that's a part of a production website, you care about what your system actually does. And so you end up solving these problems in practice. My observation is that I think the academy is not doing a good job of tracking what's actually happening there. And I think that because of the way we view problems, things that are actually part of a broader pattern of failures are treated as one-offs.

**Josh Albrecht:**
Do you have any ideas on the academic side how to help correct that or counteract that, or things that people can do, or interesting research, directions for them to explore?

**Dylan Hadfield-Menell:**
I think basically for all your research you should be able to talk about the system designer in some way, and view your tool as in some way relating to an actual thing that you care about. I think we should be moving away from strict quantitative performance measures, and moving in towards qualitative evaluations of systems. From that point, actually building in more qualitative evaluations into our processes directly. So I have had the interesting experience of both learning to do deep reinforcement learning and trying to teach people to do deep reinforcement learning. And it's really hard. It's really tough. It's a combination of a really challenging software engineering problem with neural nets and TensorFlow with just this kind of optimization intuition that you have to develop. And it's all done at a really slow timescale, and depending on where you are, you can waste a lot of money very easily.

**Dylan Hadfield-Menell:**
And so it's quite literally costly to experiment on in many ways. I think it's really hard for people to learn in that environment. But one of the biggest errors that people make early on is an over reliance on quantitative measurements. They're used to working in the CS where there are clear test results, and you get your numbers, you can see them. And we train people to be like, "Oh, your numbers are your numbers. Don't bother rerunning the code, it's not going to change anything. Your numbers are your numbers." In deep RL that's not quite as true. And what's the process that you have around the metrics that you use to evaluate your system I think is something that we don't teach very well, that I hope we will teach more in the future.

**Dylan Hadfield-Menell:**
With my students I've started taking a pretty direct approach to when you build your system, you have this evolving set of quantitative metrics, and when you evaluate an experiment you always build in some degree of manual review of some component of it, during which you try to scan through failures, identify failure modes. First, you can track by hand how often those are, and if you can come up with metrics to capture those, integrate those into your process, and continue repeating this. What I've found is that this little bit of structure actually makes a pretty big difference. And again, I think most AI researchers who succeed have something like this, either directly or indirectly, that they're doing. It's not magic. We don't teach that as part of the process of designing and building these deep RL systems.

**Josh Albrecht:**
Right.

**Dylan Hadfield-Menell:**
You don't see that in textbooks of, "Run this, and then let's talk about some analogy to unit testing for this." And I think when you evaluate deep RL systems, there should be an evaluation of how long it takes an intermediate level undergraduate to deploy this onto a new environment for a different suite of environments. There's the overall performance you get to in the end, but there's the complexity of deployment and the software engineering complexity building this, and testing this, and iterating on it. I think as we start to pay a bit more attention to those metrics, and thinking about tying system performance to qualitative evaluations, and having that be, "This is the problem we're solving," that will start to shift us in the right direction.

**Kanjun Qiu:**
One thing I wanted to ask earlier was you had mentioned this analogy of the machine learning models that we're building today a good comparison is to compilers when we first started doing the programming. And so what we need now is the general purpose programming language. How would you characterize the analog of the general purpose programming language in machine learning?

**Dylan Hadfield-Menell:**
Our analog is something like a labeled dataset. It's a representation of an objective. It's a ranking of different possible behaviors where those behaviors are encoded as the weight to the neural net, the parameters of a policy, something of that nature. We do have something like the general purpose programming language today. I think the supervised learning dataset, ImageNet is, and this analogy looks like Python, or C, or something like that, and it's a large representation of a certain type of behavior. And then that can be compiled down into something that we can execute

**Josh Albrecht:**
And hence interest in weekly supervised stuff, because then it's really how do we make the higher level language instead of having to label all million of those images by hand? Could we instead say, "Oh, okay, I'm just going to pick a category, and now I do a few, and now I can make a whole new ImageNet in a much faster amount of time. Express my human preferences or desires for this system in a much faster way."

**Dylan Hadfield-Menell:**
Precisely. I think data augmentation fits into this quite well. It's a way to take your data, which is an objective, a representation of rankings, of different behaviors. You can augment it to make it a different objective that encodes desired and variances in your prediction model. And if you think about that's really a very explicit encoding of desired properties of the output behavior.

**Kanjun Qiu:**
Yeah.

**Dylan Hadfield-Menell:**
And it doesn't fit into the standard stat.ML kind of model per se. It's not new. I mean, it's sort of is new label. To me it makes a lot of sense when you think about it as, "Here are properties of the final behavior, and we want the prediction to be such that gray scale doesn't change the output." And what's a good way to change that, to enforce that? Well, the same way that we are teaching it that a cat is a cat, is also have great scale cats, and those are for cats.

**Kanjun Qiu:**
Mm-hmm (affirmative). Interesting. Another question I wanted to ask was, so given the research direction around AI safety and compatibility, do you have any concerns with the way that the field is progressing at the moment?

**Dylan Hadfield-Menell:**
I think it is quite possible to make a lot of money with what we would call more shallow metrics. Optimizing for engagement or watch time is really effective. It has a lot of negative externalities, which are hard to measure. And so I think that AI systems have a bias towards optimizing for what's easy to measure. And I think that that can be incredibly valuable to companies running off towards a world where resources from things we care about are slowly recruited into shallow measurements of value, where perhaps we're not even very aware of what's going on. I view that as a real threat to human flourishing or what have you. And I think there's good evidence that that's what's already happening with many of the systems that are currently out there.

**Josh Albrecht:**
Mm-hmm (affirmative). But the dangerous thing is that it works in the beginning. You have this upward trajectory in the very beginning of re-optimization, "Oh, everything is getting better. Look at these. Let's do more." People are very much have the like, "It's working. Let's do more of the thing that's working."

**Kanjun Qiu:**
Right.

**Josh Albrecht:**
But the problem with this is what works, then it stops working as well. And if we don't really…

**Dylan Hadfield-Menell:**
Well, and it's not clear we will recognize or be able to stop things at that point. There's a kind of screenshot of one of these textbooks stories that I've seen around on Twitter that talks about the phenomenon of temperature. Apparently back in the 1700s philosophers argue, there's a reasonable amount of debate on whether we could ever measure temperature. When you hear this it's a little bit absurd from the modern perspective. And then you can look at what their arguments are about, and their arguments are about, "You'll never be able to tell the difference between a damp cold, and a dry cold, and a musky heat, and it goes on and on through all these different things. And what you begin to understand is that what they meant by temperature was something about the experience of weather or the experience of an environment. And they meant it in this sort of what's the inner subjective quality of all of this?

**Dylan Hadfield-Menell:**
When you realize that you realize, "Oh, we have not been able to measure that. We have temperature, and we have windchill, and we have humidity, and we have all these different things. And we know that they all don't fully capture everything, and we still have these loose categories that we tell other people about." What there's evidence of is it something perhaps a little bit insidious? You had this rich qualitative property of the world, which was grounded in experience and subjective experience of the world. At some point, someone realized you could have a really useful signal that was very related to that, which was the average energy of atoms in a substance.

**Dylan Hadfield-Menell:**
Over time, the definition switched to being this concrete, measurable property. And now how problematic you seen this version of the story. I'm not sure we still experience temperature in the way that they meant it. We still get different types of cold. We still have words to talk about it. It's still a very human side of things, but this type of phenomenon, and this ability to redefine things of value as shallow alternatives is something that's troubling when you think of that AI systems.

**Kanjun Qiu:**
Right. It's like the important thing is it is helpful to loosely define that some of these things in terms of things we can measure, so that we can communicate them properly to other people, but also there's some kind of human value component of it that can't be lost. It's important that it's not lost.

**Dylan Hadfield-Menell:**
It's important that we've also developed humidity, and we also have wind chill, and we've got like a bunch of these factors that allow us to have a more interesting conversation than we could have before. Where we have these objective things that we can point to to draw similarities between.

**Kanjun Qiu:**
Right.

**Dylan Hadfield-Menell:**
And the ideal humans flourishing with AI in the world story is one where we're iterating on what these measurements are. And we're building this broad set of growing measurements that capture our best attempt to understand what we care about in the world.


**Kanjun Qiu:**
Mm-hmm (affirmative).

**Josh Albrecht:**
Mm-hmm (affirmative).

**Dylan Hadfield-Menell:**
I think that a world where we can do that effectively is one where I feel good about our ability to build systems that work well, and are beneficial for society broadly.

**Josh Albrecht:**
Is there anything else that you can say about how to help move towards that future? I feel like the majority of people are probably not thinking about, "Oh, how do I measure these very difficult unmeasurable things?" And as you said, it's a lot of work, and you have to make these all datasets, and it only happens later. 

**Dylan Hadfield-Menell:**
So I think there's work going on this in several ways. There's academic work at trying to elicit these types of things. Ultimately, I think a lot of that is slaying at the margins. I think the big answer for how we do this has to do with how we build the next marketplace of AI systems and AI services. One way to think about these measurement problems is there's something like a market inefficiency. You have people that are using AI systems that care about subjective properties of the world, and they would prefer that be included in their system.

**Dylan Hadfield-Menell:**
And this might be that I don't want to see anti-Semitic posts in Facebook, or it could be properties of YouTube content that you want to manage in some way. I think that in the future, we would be better off if we can think of companies like YouTube as facilitating a transaction between consumers of ranking information or measurement information who are users, who want to see a video that's truthful, and interesting, and inspiring, and businesses, or nonprofits, or organizations generally that work to come up with measurements of those properties in the world.

**Josh Albrecht:**
Two thoughts off of that. One, it's really interesting to think, "Oh, okay. How could you enable people to do a better job of using YouTube in a way that they want? Can you have your own filters that go off, and do things and express your own will, give people more tools, more power to do that?" That's kind of interesting thought, and I'd love to hear your thoughts on that. Also, "Oh, no. What if you do that? Do we really trust people to actually do that? Or are people going to go off in crazy directions once you give them that?" I think that's also an interesting…

**Dylan Hadfield-Menell:**
Yes. So there's a real collective regulation problem there as well. I tend to think that system is more regulatable than the current one.

**Josh Albrecht:**
Which system is regulatable?

**Dylan Hadfield-Menell:**
If you have a world where there are lots of metrics being provided, and we can facilitate something like a marketplace where you can choose between different metrics that decide how AI systems should interact with you, that provides an ability for the clear legitimate role for a platform in a scenario to control which metrics are allowed and aren't allowed on the platform, and what are the bounds for how a metric can be incorporated into your preferences. So for example, maybe you're not allowed to turn the, "I want Fox News content to a 100% or 0%." Maybe there is a certain set of things where for the good of the overall platform, you restrict the user choices to include some sort of group cohesion as part of your mandate. I think there's a lot of questions about what you would actually do, but if we can deal with the problem of verifying users, it seems like verifying metrics is doable. And the alternative seems much worse in the sense that metrics are defined and maintained internally.

**Dylan Hadfield-Menell:**
I think one of the major challenges that we have is how you scale processes around managing metrics for AI systems to global internet platforms. The things different communities care about are very diverse. I think Facebook's examples with hate speech, and different versions of hate speech, and violent speech globally, and their ability to respond to that is really hampered by being a centralized organization. And I think if you wanted to truly solve that problem, you would need to have localization teams within your company deployed to all of those places, tapped into various parts of civil society. And even then, it's not great because the decisions those teams have to make are incredibly political.

**Dylan Hadfield-Menell:**
And so this is where I think having a distributed solution where there are clear rules for what types of metrics are allowed. There's clear moderation process at the metric level, not at the content level. And then content moderation is largely handled by these locally created metrics, seems like one of the only ways that you can scale control of one of these algorithms globally. I think otherwise you're going to see balkanization, and balkanization may not be bad in the sense that you can still have connections between different networks. If you can figure out how to connect between different jurisdictions, then distributed control may in fact be a lot better.

**Josh Albrecht:**
Not the answer Facebook wants to hear.

**Dylan Hadfield-Menell:**
Not really, but I think Facebook is in a position where they actually could probably do the localization. The problem is they’re one of the only companies in the world that can. I think the nice thing about this decentralized market style solution is that it enables smaller companies to still use sophisticated measurements of value.

**Josh Albrecht:**
Yeah. So it doesn't all need to be just part of one of the biggest five companies in the world.

**Kanjun Qiu:**
One giant system.

**Josh Albrecht:**
Yeah.

**Kanjun Qiu:**
Yeah.

**Dylan Hadfield-Menell:**
Yes.

**Josh Albrecht:**
That's a really good point. We're just giving people more metrics, more ways to express their values and think about what do we actually care about.

**Dylan Hadfield-Menell:**
Yes. Now the problem is actually getting people to think about their values, and express what they care about, and learn all this complicated stuff is really challenging. If I could wave a magic wand and do things, I actually think platforms would run paid studies for their user base to identify how to set these defaults.

**Kanjun Qiu:**
It's just like a design problem. In normal product design you also have to do this to make it usable.

**Dylan Hadfield-Menell:**
Yeah.

**Kanjun Qiu:**
Also very complicated. Helping users understand their objectives is also a design process where you should go through the same…

**Dylan Hadfield-Menell:**
And it's like understanding what the system can do, and what you can do with the system, and how to communicate what you want it to do. I think if you can do that, that's sort of the basics you need for marketplace. Now there's a famous study that looked at consumer happiness with choice. It's called the "Jam Study."

**Josh Albrecht:**
Yeah.

**Dylan Hadfield-Menell:**
Yes. So what happened was they looked at how many different choices of jam people could select between as customers. If you're an economist with ECON 101 under your belt, there's this nice sub modularity property to how happy people are. Because you give them more options, they should at worst still pick the same thing and be happier. And what they discovered in this study with jams is that's not true. If you gave people lots and lots of choices, they were more unhappy in the future.

**Dylan Hadfield-Menell:**
Again, I think this is one of those things that's a paradox to economists, but as people makes a lot of sense.

**Kanjun Qiu:**
Mm-hmm (affirmative).

**Josh Albrecht:**
Mm-hmm (affirmative).

**Kanjun Qiu:**
We don't really understand exactly what's the reason why all this is true. There's lots of hypotheses, but I think what this points out is some of the fundamental challenges of complexity in a marketplace. One of the key problems with recommender systems in particular and AI systems more broadly is the set of things they can do is fundamentally complex. The number of possible news rankings that I could see for my Facebook feed is a lot. It's a lot for me to wrap my head around as someone who's doing research in this space. So how you actually manage consumer education and information, and build the prerequisites for an efficient marketplace into this is really challenging. Those are some of the big questions that I'm thinking about around design, and deployment, and management of AI systems.

**Josh Albrecht:**
Do you have any hope for that? That problem seems really hard. If you've thought about this for years now for content recommendation, and it's just sort of an overwhelming problem of, "How would I want these things recommended or ranked? And how can my mom possibly do that?" How do you ask someone on any expertise to do that? And not just for one place, but across a huge number of different places, right?

**Dylan Hadfield-Menell:**
One of the goals of this metric set up is that it should give you ways to delegate that expertise to trusted institutions, which is one of the ways that we've tried to do this. And my hope is that some people would have metrics that are like, "We're psychologists, and we study how to make sure you have a balanced information diet and are happy. We provide metrics that do that. And we recommend you just subscribe to our metric, and then incorporate a few other things for things you like." And you could imagine that being helpful. I think we help people make complex decisions in lots of ways, we're not used to having societal systems in place to help people manage information intake. There are lots of creative things you could think about here though. One would be so for family members, I actually think, obviously this doesn't work for everyone, but the notion of delegated recommendations or delegated trust within social networks seems like a valuable idea here.

**Dylan Hadfield-Menell:**
We already have a pretty clear notion of how this could work for parents and their kids. For people under 18, I think in a world where we have actual user control of recommendations, you would have parental control of those recommendations. Similarly, I think my family would like it if we could delegate control of my grandma's Facebook account to my cousin. We all run an IT support team anyways, and we may as well just reify that and build it into the system. Like everyone from our generation, this is a thing that we're doing. Different people are blessed with grandparents or parents, and those family members have differing levels of technical expertise and will. And if they're not interested in it we work with them around that. And these are types of things that ML systems and AI systems can-

**Dylan Hadfield-Menell:**
And these are types of things that ML systems and AI systems can draw upon as well in how we make decisions about how to interact with them. Another kind of interesting creative idea here is a notion of something like an information doctor. We see people who are like nutritionists or physical therapists or general doctors to manage really complex decisions about how to manage us. That might involve seeing a therapist to learn more and improve on like our individual behaviors. It might... seeing nutritionist to improve, our sort of actual diet. It's fair to think about something to that effect for our information diets too.

**Kanjun Qiu:**
That's really interesting.

**Dylan Hadfield-Menell:**
One of the really cool things about machine learning is that as we start to do more things like this, this can have positive externalities on the rest of the system. So A, when I talk about this, I do tell everyone that you should spend five to 10 minutes a week thinking about your internet information consumption and what would you like it to be and how to activate more like that, because the systems are all behavioral. If more people start acting the way they want to, you can actually speak it into existence in a very real sense. But Wall Street vets learned this.

**Kanjun Qiu:**
Totally, actually very interestingly, Josh invented an information diet system for himself. We had an assistant in the Philippines, and he basically gave her thorough instructions every week on how to adjust what sources he wanted and what she should be looking for. And she-

**Dylan Hadfield-Menell:**
Oh, that's fantastic.

**Kanjun Qiu:**
It's really interesting.

**Josh Albrecht:**
Right? I can just filter out all the stuff that I didn't want. And the idea was like, by having her do this and expressing it through this doc, I can build up labels. Someday, I can automate it. For now, I don't care. 

**Dylan Hadfield-Menell:**
Have you thought about having her control your Facebook through see less often or things like that?

**Josh Albrecht:**
She's the only one who goes to Facebook. I don't go to Facebook. She only goes... Facebook is read only. And I will maybe write if I see something in there where it's like, oh, respond spot and help a friend or something.

**Dylan Hadfield-Menell:**
So she does actually filter it. So I think it would be fascinating if you were able to build that data set of that type of information. If you think about it, there's the positive externalities from a lot of people doing something like that or using the data like, that could be huge. If you imagine that an individual is going to have to do all of this on their own, which is tough.

**Kanjun Qiu:**
Quite a bit about how would we allow someone to express such preferences. And it was in quite late. So the complexity began very quickly and we were like, there's no way that any normal person would use a tool like this.

**Josh Albrecht:**
But I just like your solution, like delegating to other people, information doctor like using the social ties. I think they could see a lot more.

**Dylan Hadfield-Menell:**
Yeah. I want to be clear though, that I think the best solution here is to just pay for it. If users understood the value they could reap from these systems, the calculus changes. No one's willing to invest the effort in these things. It's something that tech executives say a lot in this space. And like in recommender systems, there is a shift truism, no one uses controls. Like people can play it a lot about recommender systems. You do have a really fine grained level of control over how recommender systems interact with you. Not obvious how to use it. It takes time to use it's complicated.

**Kanjun Qiu:**
And there's no feedback.

**Dylan Hadfield-Menell:**
And there's no feedback. So I think the fact that you don't have this predictive model of how things will change, you don't have a good handle on what can the system actually do. And how can I express which of those things I would like to have, happen as long as that's true, these tools don't work. But if you can break that, get more people around who understand, oh, here's the space of options. Here's how things can change. Then they can start to take actions that are reflective of the value of those behaviors to them. And that's really what you need as a signal within the system.

**Josh Albrecht:**
Yeah. And similarly, if you can allow people to take more leveraged actions. So to the point that we can to provide stuff, yes. So you can go into Facebook and there's a thousand different controls, but if you see something and basically I just don't want to see stuff like that anymore. And you can like very easily express that. And it like feels obvious, easy how to like express what you're talking about. Maybe more people up into it. It is a question though, a lot of them already are like, oh, don't recommend content like this. And I think how many people really click on those? So even if it were super easy.

**Dylan Hadfield-Menell:**
I don't think a lot of them have those options. Those systems are not very used. The way I understand that in part is those systems like show less often represent something like contracts to the user. You are taking an action and in return, the company is committing to, well, do what exactly?

**Kanjun Qiu:**
A lack of feedback problem. We don't know what the other end of the contract is. That's actually on my paper or the incomplete contracting.

**Dylan Hadfield-Menell:**
Yes. That lens plays a big role in my work. And that incomplete contracting line of work grew out of the principal agent literature in economics. And specifically, it looks at the challenges that arise when you can't specify a perfect contract on performance incentives. For this reason, I think it's very related to AI systems and machine learning, where we have incomplete contracts with our systems.

**Josh Albrecht:**
Yeah. It seemed like a really interesting word. What did that turn into eventually into that sort of line of research turned into anything or go anywhere? Are there people pursuing it or did it turn into the most recent they're upstate?

**Dylan Hadfield-Menell:**
I think the most recent nerves paper is the most direct follow on to that line of work. It also plays a bit of a role in some of these ideas around having diverse sets of metrics that you can include, what the metrics serve as is terms that you can use in a contract between yourself and the system, which takes the form of incentives. This is where the terms need to be human. So that's where having institutions that can define them and manage PR campaigns to convince people about what they actually mean and what they represent and to define those terms in an ongoing way as the world progresses. I think it's really interesting actually, that you have someone who's, you hire as an information filter because it actually creates this very real personification of a job we give to AI systems all the time. If you think about the ways that you communicate your preferences to what's this person?

**Josh Albrecht:**
Paula.

**Dylan Hadfield-Menell:**
Yeah. Okay. So if you think about how you communicate your preferences here to Paula, and there's a lot of interpretation, there's a lot of shared knowledge of the world that you draw upon. If you've said, so don't show me things with hate speech. You would expect that to draw upon a bunch of common sense and you would expect it to be an evolving mutable definition that you can impact in the future. And you have clear ways that you can change that and update that you have confidence. You can make those changes. If we think about how you might express this to an AI system, it's difficult to see sort of a priori, if it's your job to define all of that context, that's too much work. But I think if there's an existing metric that's published, there's several metrics published by different organizations.

**Dylan Hadfield-Menell:**
The one that I was using, my stories is SPLC for this. If you imagine the SPLC is tracking a set of different hate speech metrics with evolving submissions, from people of "Hey, there's this new anti-Semitism thing", that's just like Jewish based laser stuff. So that now gets included into the metric and that can evolve and grow as well in this case as hate speech evolves and grows.

**Josh Albrecht:**
Yeah, exactly.

**Kanjun Qiu:**
Yeah. I had another question earlier, which is, you mentioned you're a little bit concerned about how unsupervised learning or self supervised learning is actually progressing.

**Dylan Hadfield-Menell:**
Well. So unsupervised learning and self supervised learning. I guess my answer to that question is, I happen specifically. I think unsupervised learning represents a desire to push AI further and further towards learning objective properties of the world without a strong normative component. There's a lot about unsupervised learning, which is about the assumption that the data that you want just sort of already out there and all you need to do is find it. If we think about that hiring example, you shouldn't walk up to that data set and assume that you are hiring examples are clearly defined by a couple of metrics there. If, in fact the ideal hiring process is clearly defined by a couple of metrics. You'd like a process that identifies that quickly and leverages them yeah.

**Kanjun Qiu:**
Doing unsupervised learning and curating the data set that was being learned from then you'd have...

**Dylan Hadfield-Menell:**
If you're paying attention there, that could make sense.

**Kanjun Qiu:**
Right?

**Dylan Hadfield-Menell:**
I think my concern is that we should be looking hard at trying to grow the bandwidth of what should the system actually do. How do we verify if the system is doing the right thing, how do we carefully deploy that and roll that out and manage these behaviors as they're deployed. And I see unsupervised learning as quite powerful, but largely about growing this pipeline towards understanding the world without understanding what's right or wrong.

**Josh Albrecht:**
Yeah. It's almost an orthogonal direction. That's like increasing the capabilities of world understanding and decking patterns. And that's, that's all great in a sense, but there's also this other whole different direction to travel, which is we should be thinking about the whole system. And there are so many fewer people thinking about how does the whole system, what even data should we be doing unsupervised learning on why are we even granting first place? There's so many more of those questions to be answered as especially as we make these more powerful.

**Dylan Hadfield-Menell:**
I think that's right. Unsupervised learning seems like a really good candidate for how to learn what people will do online without actually learning what they should do or what you should do in response. In relation to that, I think if you look at large language models, those are trained and largely unsupervised ways, those models display a corresponding lack of any normative concept. The goal is to reproduce the data. There's not that much nor end of thought, going into the data or what's good or bad there. So some of my recent projects have been looking at, manipulation and that is something where these types of concepts start to get quite complicated. We don't even have sort of good mathematical theories of what it could look like of like a person that could enable manipulation in a way, what does it mean to measure manipulation or prevent it, or keep it from happening is really tough.

**Dylan Hadfield-Menell:**
And it's something you can look at on a case by case basis. We're currently in a scenario where all of the research that could be happening on these systems is either happening at relatively slow paces in public or within companies in private in ways that they're not likely to publish quite so much where they have strong economic incentives not to. And if you think about, I think it's YouTube search optimization for watch time. I mean, you can look up some of their blog posts around this. If you think about optimizing for watch time, that includes incentives to manipulate and a bunch of ways around content and around how people are going to behave and what people are likely to do. And so you have to imagine that these patterns for manipulation are present in the behavioral data and they're likely being taken advantage of and some way or another, we don't really have a good way to understand what's going wrong or how it would be going wrong.

**Dylan Hadfield-Menell:**
And we don't really have the systems in place to create incentives to work on what's going wrong. And the people in control of the data have really strong incentives to look the other way and already sort of made it clear that the PR plan does involve saying as little as possible and making all these things trade secrets.

**Kanjun Qiu:**
And also one tricky thing about manipulation is that inherently manipulation is a measure of the diff, between what the person wanted, like intended some kind of like intrinsic interest versus what that person was caused to do. Finding their intrinsic interests seems quite difficult.

**Dylan Hadfield-Menell:**
I've been working for awhile with mathematical models of preference shift and defining manipulation. For those of abstract entities is incredibly challenging. What you have that system behavior, you have a sequence of preferences that change, and then you want to ask, is that okay or not? We've got some proposals in a pre-print that we're putting together that we're, we'll be submitting soon. The short answer is we don't really know. We can measure deviation from a baseline in this theoretical example. So maybe that's good. There are other properties in our model that seemed good, like accuracy of agent's beliefs, but manipulation is a good example of something where we know it when we see it.

**Dylan Hadfield-Menell:**
And so to that end, it's something that AI should be able to work with. And I think if you wanted to really tackle the problem, working at a large company, you could imagine systems that would work with people to do weak labeling and weak supervision on behavioral traces to identify and baseline against a certain degree of non manipulativeness. Not as something that is that perfect. No. Do we think that we could build tools that people could work with to do this type of labeling? Yeah. Could they do it economically at a scale of YouTube where they would need to work to make their system so profitable? I don't know. That answer is probably why we're not going to figure out how to put these systems into place in the short term. I'm a lot of fun at parties, did I say?

**Kanjun Qiu:**
Yeah. One thing I forgot to ask you earlier when we were talking about how you got to your current research is whose work has impacted you the most or what papers or what work have you spent a lot of time meeting and digesting? You mentioned incentives class and senior college. So there's that.

**Dylan Hadfield-Menell:**
That class in particular and paper there on misaligned performance incentives by baker is a particular one. That's always struck me. There is a paper it's a home Strum in the Milgrom and it looks at multitasking and the ways in which providing equal incentives on tasks that are differentially measurable, creates misalignment in an agent's behavior, where they overinvest in the measurable task and their model. It's a natural consequence of risk aversion that has stuck with me a lot as I think about all of these things. One paper that I just has a great title is on, "The Folly of Rewarding and Hoping for B". It's one of the Seminole papers and principal agent problems. Its just so beautifully self-explanatory.

**Kanjun Qiu:**
Such a great title!

**Dylan Hadfield-Menell:**
That it can not be a favorite as I think about more modern work. I don't know if this is specific to my work per se, but data set aggregation, where is that paper and imitation learning that I just think it was a fantastic idea.

**Dylan Hadfield-Menell:**
It captures a lot of what's going on and more directly in imitation letting paper. But to me it explains a lot of how AI systems can go wrong when they're deployed. The core idea in the paper is if you are using a supervised learning system with bounded error to do imitation learning, the error rate grows as you execute the policy for longer and longer, because the distribution of data deviates from the training distribution, as it shifts towards the expert distribution, you have this error that builds up in your distribution and pulls you further and further from the expert distribution and provides this elegant answer, which is to go back to the expert and just get the right thing to do. When the evolving data distribution, it's totally obvious, but they prove it rigorously. It's done really nicely. They had a really nice paper that they did this for where they were training a drone to fly through a forest.

**Dylan Hadfield-Menell:**
The answer was the first thing you do is you have people fly the drone through the forest. Then you have the drone learn to imitate them and you let it run and you have people control it, but you disconnect the joystick from the actual controls. So they're controlling it, but they're not actually doing anything.

**Dylan Hadfield-Menell:**
The drone goes through with crashes, but every time it crashes, it gets data about how to avoid a crash. And it's relatively cheap. The drone is flying relatively slowly. It was pretty sturdy. It wasn't that big of a deal for it to crash. Eventually, if you do this, you actually pretty reliably ended up with a system that can fly through the forest. It sort of relates to different types of failure, mining and supervised learning systems, but for sequential systems in particular, I think this is a really important realization of you're shifting the overall distribution that you're testing on. So, you have this constant need for supervision and tying things back to the supervision signal in this nice way that's cleanly analyzed. It's one of those papers that shapes a lot of how I think about things. And it drives my intuitions for working on AI systems, if not the direct applications.

**Kanjun Qiu:**
Yeah. Do you remember what the speakers?

**Dylan Hadfield-Menell:**
Data set aggregation? I think Drew Bagnall is one of the authors.

**Josh Albrecht:**
The title was just data set aggregation.

**Dylan Hadfield-Menell:**
I think. Yes, I believe so. And that goes by the acronym dagger. If you see it in other places, those are pretty large influences for me in my work. The other direction is just coming from a background and mark off decision processes and Palm DPs. So I tend, think about things from sequential perspectives. Usually there's some decision-making process or some decision-making setting. And so I always try to understand those at different levels of abstraction when I'm working on a problem.

**Kanjun Qiu:**
Cool. Was there anything else you wanted to talk about that we haven't covered?

**Dylan Hadfield-Menell:**
No, I don't think so.

**Josh Albrecht:**
I really enjoyed it. It was super fun.

**Kanjun Qiu:**
Really interesting models and theories and...

**Josh Albrecht:**
I think that's the right party.

**Dylan Hadfield-Menell:**
It's the right party, the right parties.

**Kanjun Qiu:**
I have a bunch of different quotes from you. Like that's our way to include our desired goals. We sources are being recruited into shallow measures of values. Why would you expect this data to be unbiased? There's like a byte of stuff. That was really good. Real gems.

**Josh Albrecht:**
Maybe one last thing. Is there anything that you want to put out there or solicit whether it's collaborators or I think you mentioned you were going to be a professor at MIT soon. So you want people to apply to be your graduate students or something.

**Dylan Hadfield-Menell:**
The big thing is to read my nerves paper and email me with questions about it.

**Josh Albrecht:**
Perfect. I think it's a really good paper and it shouldn't be much more widely known. So I would definitely encourage people to...

**Dylan Hadfield-Menell:**
Fantastic. My stump speech is very much about that paper truly is something that I've been thinking about how to formalize for a while. I'm very excited to have something to point to, to talk about pitfalls of optimization and structural pitfalls and structural pitfalls, therein.

**Kanjun Qiu:**
I think it's really well done and very rigorously captures problems, people talk about intuitively, but don't have the mathematics to back it up.

**Dylan Hadfield-Menell:**
So I hope so. And I take credit to my co-author Simon on that. Who is total math wiz.

**Josh Albrecht:**
This was great, Dylan. Thank you so much.

**Dylan Hadfield-Menell:**
Yeah.  Thanks for reaching out.

**Kanjun Qiu:**
Thank you for listening to Generally Intelligent. We love feedback and questions. So please feel free to ping us on Twitter at Kanjun and at Josh Albrecht or email us with any ideas of crushes. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify or your favorite podcast app. Thanks very much. And we'll see you next time.

<br>

*Thanks to <a href="https://twitter.com/lukelivesfree">Luke Cheng </a> for writing drafts of this post and <a href="https://www.linkedin.com/in/tessajhall/">Tessa Hall</a> for editing the podcast.*
