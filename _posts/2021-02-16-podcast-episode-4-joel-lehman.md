---
layout: post
title:  "Generally Intelligent #4: Joel Lehman, OpenAI, on evolving intelligence, open-endedness, and reinforcement learning"
date:   2021-02-16 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe id="podcast-embed" src="https://anchor.fm/untitled-ai/embed/episodes/Episode-04-Joel-Lehman--OpenAI--on-evolution--open-endedness--and-reinforcement-learning-eqguml/a-a4ln5m5" width="100%" frameborder="0" scrolling="no"></iframe>

Our fourth episode features [Joel Lehman](http://joellehman.com/) ([Google Scholar](https://scholar.google.com/citations?hl=en&user=GcvxHWQAAAAJ&view_op=list_works&sortby=pubdate)), previously a founding member at Uber AI Labs and assistant professor at the IT University of Copenhagen. He's now a research scientist at OpenAI, where he focuses on open-endedness, reinforcement learning, and AI safety.

Joel’s PhD dissertation introduced the novelty search algorithm. That work inspired him to write the popular science book, [“Why Greatness Cannot Be Planned”](https://www.amazon.com/Why-Greatness-Cannot-Planned-Objective/dp/3319155237), with his PhD advisor Ken Stanley, which discusses what evolutionary algorithms imply for how individuals and society should think about objectives.

**Highlights from our conversation:**

- How discovering novelty search totally changed Joel’s philosophy of life
- Sometimes, can you reach your objective more quickly by not trying to reach it?
- Better ways to evolve intelligence
- Why reinforcement learning is a natural framework for open-endedness

<br>
*Below is the full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
<!--more-->
<br />

### Some quotes we loved:
> Novelty search is a way of looking at the question of how ambitious objectives are reached: how do you accomplish ambitious things?

> What novelty search did was ask a seemingly zen-like question, which is, "Sometimes, can you reach your objective more quickly by not trying to reach it?"

> The easiest way to talk about open-endedness is to point to some processes that we're familiar with that are open-ended. Biological evolution, for example, is an algorithm that's run for billions of years and one run of biological evolution has produced all the amazing diversity of life, including ourselves. And so, it's amazing that a volitionless process produced volition. That's what I mean by open-ended. It's continuing to create new things, diverse things, over time.

> Imagine this SAT analogy problem, which is bird is to jet as evolution is to open-endedness. The idea is that birds' flight is really interesting, it shows it's possible to fly, and maybe we even tried to mimic that with ornithopter and those kinds of machines. But really, the history of flight took off when we had some hypothesis about the core principles of flight, that enabled us to engineer things that could more efficiently do things maybe that weren't even possible for biology. You can't create a bird that carries tons and tons of cargo across the ocean. Similarly, while we might take inspiration from biological evolution, what are the core principles of open-ended creativity? If you could bottle creativity into a jar, into an algorithm, that could efficiently instantiate an open-ended process that is aimed towards whatever domain we want, that could do so really efficiently and in a way that's not like biological evolution, but actually has capabilities that are much more impressive than biological evolution?

<br>

### Transcript
**Kanjun Qiu:**
Today we have with us Joel Lehman, who is currently a research scientist at OpenAI, but previously he was a founding member of Uber AI labs and an assistant professor at the IT University of Copenhagen. His research right now focuses on open-endedness, reinforcement learning and AI-safety. His Ph.D. dissertation actually introduced the novelty search algorithm, which is really interesting, and inspired him to write what is now a popular science book with his advisor, Ken Stanley, on what search algorithms imply for individuals and societal objectives. And it's called, Why Greatness Cannot Be Planned. You may have heard of it. The views expressed in this episode are Joel's views alone and they're not OpenAI's.

**Joel Lehman:**
One thing that I would feel strongly about would be that Ken Stanley also is introduced as a co-author of that book. I don't try to take too much credit for the ideas that were jointly ours.

**Kanjun Qiu:**
Excellent point. Awesome. Well, let's get started. We'd love to hear about actually your research interests, your research philosophy to start with.

**Joel Lehman:**
My research philosophy is really entangles with the research direction that I've been involved with. And I think that might be atypical. I guess I tend to be a person who is influenced by the algorithms that I discover, and it actually gets entangled with the way that I live my life and my philosophy. I wasn't always that way. Doing my Ph.D. dissertation shifted all of my belief structures and really how I saw the world and how I thought and how I wrote. It really changed my philosophy of living and how I see research. That might be a good segue to talk about novelty search, which is what I studied then. That really is deeply entangled with my research philosophy.

**Kanjun Qiu:**
What was your philosophy of life and maybe research before your Ph.D. dissertation, and then what happened?

**Josh Albrecht:**
Yeah how did you start? What were you thinking originally?

**Joel Lehman:**
Originally, I didn't have a plan and in some ways I had tracks the ideas that ended up in this book that Ken and I wrote. I was doing an undergraduate degree in computer science. I don't think that I was really an exceptional students and I didn't know what was going to do with my life at all. When I came to undergraduate, I was at Ohio state. I was at first kind of confused whether I wanted to be a music major or a computer science major. And it was kind of this delicate choice between what seemed more practical, computer science, as opposed to maybe more risky and artistic, which would be music. I thought at the time that I would become a video game programmer. That's how I got into programming. Yeah. I think a lot of people maybe sometimes get into programming from that lens. Like you play all the video games as you're growing up and you get inspired by that to kind of study, I want to make the games themselves.

**Josh Albrecht:**
That's how I got into it. Yeah.

**Joel Lehman:**
Oh Yeah. Yeah. It's kind of formative experiences. I remember there was a magazine I used to get as a kid called, 3-2-1 Contact, an actual paper magazine. In the back of this magazine, there was listings of programs in the basic programming language. You actually type in these programs it be some kind of little animation or a game. And it's kind of this bonding experience that I had with my dad that also got me just really deeply into programming. I didn't understand what I was doing and there's all of these old floppy disks that have these kinds of aborted efforts to make text adventure games, just filled with...

**Joel Lehman:**
That were just really naive and childlike, but kind of showing that I had this curiosity. So I just really thought that video game programming would be where I would go. And somehow, while I was doing my undergraduate degree in computer science, so I ended up choosing not to do music, but to do computer science.

**Joel Lehman:**
Somehow there, I just lost interest in video games. I'm not sure exactly how it happened, but that kind of evaporated and I became much more focused on, okay, maybe I'll become a software engineer or something. I did a couple internships and they were really boring. I was like, I don't know. This probably doesn't seem like I'm really going to be as satisfied in this. And it could be just the internships that I landed. And so I was feeling a little bit kind of aimless at that point. And there was an experience where I went to the library. I had this habit of just going to the library and just perusing the stacks of books and maybe had some topic in mind. I would just go browse the books and I think I was still interested in video games somewhat. So I was browsing the library and there was a book on video game AI. I checked out this book, there was a CD-ROM included with the book. Really I'm dating myself all of these references.

**Kanjun Qiu:**
Game programming or something like this was one of those books. I've heard of a few books like that.

**Joel Lehman:**
Yeah. Yeah. So this was written by Matt Buckland, I think. There's a chapter on neural networks and evolutionary algorithms. And it was really interesting to me. Really with it kind of the life-changing moment was on the CD-ROM you could run a demo and seeing in real time I'm an AI agent that was being controlled by neural network. And it was those, the weights of that neural network and the topology of the network were being evolved by this algorithms called NEAT. NeuroEvolution of Augmenting Topologies is the algorithm that my future Ph.D. advisor created. And just seeing in real time, these kind of little Minesweeper robots that you could see them clearly adapting generation over generation, evolution. And it was just really amazing to me and something just kind of snapped into place. I took an AI course in my undergraduate and there also got a little bit more in-depth into neural networks and evolution algorithms, but I really got excited by that. That evolution a brain basically seemed like a formula that could lead to AI.

**Joel Lehman:**
And so that's really what got me interested in it. And I applied to grad-school kind of inspired by that. Applied to a couple of schools and one was to University of Central Florida where Ken Stanley was then a professor and he wrote a neat algorithm. And I was then working with him. What I thought I was going to be working on was kind of the seeds of what we call open-endedness now. And he had the seeds of an idea for something called novelty search that we kind of developed together. Yeah, it was just amazing. Just how over the course of one-on-one meetings with the same person over the course of I guess five years, your entire philosophy of life can kind of shift.

**Kanjun Qiu:**
How did novelty search impact your philosophy of life? What's the before and after?

**Joel Lehman:**
There's a little bit challenging for me actually to think about how I saw the world beforehand. I think maybe the fairest thing would be to say is that I had a kind of disjoint philosophy of life. I didn't really probably have a deep hypothesis about how the world worked or how research worked, but I had a kind of cobbled together philosophy that probably wouldn't stand much scrutiny.

**Joel Lehman:**
And that's part of what I think I learned in these one-on-one meetings with Ken was that I needed to have a rationale to motivate what I was talking about. And so I would go in there with an idea and it was almost kind of like this sparring match, not in an adversarial sense, but where I would think that I had it like maybe a really profound idea. And then as we dove into the actual rationale, it would just kind of collapse. It was really humbling, but also it really honed this kind of critical thinking skill that I think now is one of my biggest strengths as research [00:06:50], to have original thoughts. You have to be able to deconstruct them and make sure that motivation is something interesting or new, or that's strong enough to survive outside attack.

**Kanjun Qiu:**
You and Ken developed Novelty Search together. It sounds like Novelty Search was a much more coherent framework for thinking about life and the world. Josh and I used Novelty Search after we pivoted our company and it was extremely helpful. We grew up in the society of believing that we should know what the final objective is and everything we do as an optimization toward the objective. But as we started going down the route of this pivot, I think it became very, very clear that no company in the very beginning ever knows what the objective is. And it is actually a discovery process to understand what you're trying to do and what the opportunities are.

**Kanjun Qiu:**
It actually changed me in some really fundamental way. I realized, oh, I have spent all of my life trying to optimize for these known objectives. That's not where most of the interesting stuff comes from. The interesting stuff comes when I pay attention to what's around me and what the opportunities are. I can imagine how it may have impacted your life and I'm actually really curious to hear, what are the things you wouldn't be doing now, if you hadn't done this?

**Joel Lehman:**
Let me start maybe by talking about what Novelty Search is, how it could lead to kind of a philosophy of life and how it actually impacted my life and how probably I wouldn't be where I am today without embracing some of the ideas of Novelty Search in a more kind of lived experience way.

**Joel Lehman:**
Novelty Search, you can view it as a kind of philosophical thought experiment in some ways. One way I like to think about algorithms is as grounded, philosophical thought experiments. I like philosophy, but I find some things about philosophy kind of frustrating. You can be very ungrounded and there could be no answer to whether utilitarianism or deontology is true because it's not specified well enough that you could actually live your life by that thing in a kind of coherent way. I think Novelty Search is a way of looking at the question of how you accomplish ambitious things.

**Joel Lehman:**
So when you think about AI, a lot of the objectives we set out for AI are quite ambitious. And so I'll be talking mostly from the framework of reinforcement learning. We have an agent and then you want to train it to do something really complicated. In most AI settings, you start really with a kind of a random scrambled brain. So a neural network that has no knowledge in it. And you want to bootstrap that up to a brain that has a lot of finally encoded knowledge that will control an agent to do something complicated, like maybe to learn to walk or to run, and most ambitious thing would be to have really profound intelligence like a human does. So do you imagine starting from scratch and trying to get to some kind of sophisticated behavior? That is sort of an ambitious undertaking and the traditional way that the machine learning that people have tried to train neural networks to get good at tasks, is starting from scratch and setting a specific objective, like do well at walking by this metric or something.

**Joel Lehman:**
And just optimizing. You basically are implying that there's a straight line path from the beginning to this thing you want. What Novelty Search did was asked that seemingly zen-like question, which is sometimes, can you reach your objective more quickly by not trying to reach it?

**Joel Lehman:**
It seems paradoxical. So could an algorithm that's not trying to reach a goal, actually reach the goal quicker than an algorithm that is trying to reach the goal? So turns out like why it might seem on the surface kind of paradoxical. It really isn't. And the reason that it's not is that we kind of, I think, know this lesson already in some facets of life. Why would we have basic research? Why would the government put money to that? We don't know exactly where basic research goes, but it will lead somewhere. And probably the net output of the money you put into basic research will strip what you put in, so there's some benefit to that, even though you don't know where it's going.

**Joel Lehman:**
So novelty search is about this idea of 10 algorithms that don't know where they're going, sometimes actually find things that you couldn't find by directly looking for them. And we kind of ground it out in a very simple scenario. There's a robot and amaze, and the robot is trying to get to the end of the maze. And if the maze itself is kind of deceptive, like there's a dead end within the maze, then an algorithm that's directly trying to reach the end of the base will just get stuck in that dead end, whereas an algorithm that's trying to search only for novelty, to look only for behaviors that are different than what is encountered in the past. So just to basically find a policy leads everywhere. So a neural network can get from here to there, to everywhere within the maze.

**Joel Lehman:**
And it turns out that that kind of algorithm will solve this maze consistently, this kind of deceptive maze, whereas the more direct objective searching algorithm will nearly always get stuck in this dead end. And so it is just a concrete example of when this kind of paradoxical, not looking for the goal, can find the goal. So it's interesting in its own right. And then I think the crux of the argument is actually in the analogy between this deceptive maze and problems we actually care about. So we don't really care about trying to find a robot that gets through a maze, but the argument is whether or not real life problems have this structure. Where going for the obvious, the seemingly obvious solution, the path will actually be a dead end. I think that actually is the way that a lot of ambitious real problems are structured. And when we kind of expanded this idea into a book like treatment, we kind of detailed a lot of these different situations where these dead ends can arise.

**Josh Albrecht:**
I would recommend that people read the book because it's a really good book.

**Kanjun Qiu:**
Yeah.

**Joel Lehman:**
Yes. Read the book. The book's great.

**Kanjun Qiu:**
It's interesting. You mentioned that the question is are some real life problems structured in this way where it's like an amaze with a dead end. And even when we look at research, it seems like research is structured this way. You see these kind of dead end branches of the research tree that eventually get pruned because we have, right now at least, sufficiently novelty searching research process. How did it impact you? Did you make any decisions differently than you would have otherwise?

**Joel Lehman:**
Once I internalized this idea, I think there was an internal struggle over internalizing this idea that, sometimes succeeding at something means letting go of directly trying to achieve that, at least in the short run, because it does go counter to a lot of the received wisdom, and I think implicit kind of cultural messages we receive. And so it was, I think, difficult to wrangle with that internally. But once I did, the clearest examples would be versed in research. Like you just mentioned that there is an analogy between something like novelty search and how research works. There are numerous examples of technologies where the potential of them was not immediately evident at the time. And maybe most obvious for talking about machine learning, is that of deep learning itself. The technologies of backpropagation and of multilayer neural networks have been around for a long time. But it wasn't until certain stepping stones snapped into place, having enough compute, tricks like the ReLU and so on, that it became clear that, okay, you can actually can train these networks at scale and it's extra qualitatively different. And this is really exciting.

**Joel Lehman:**
Now it's the next big thing in machine learning. Just to put that into context, when I was going through grad-school, no one really cared about multi-layer neural networks. They thought the received wisdom was local optima are just too pervasive. It's not going to ever work. I think the nerves conference, which was then called NIPS, it was dominated not by neural networks, which is strange because it has neural in the title, but I think by... Statistical kinds of machines, like a SVMs and things like that. So it's interesting to watch the tides of machine learning shift. It's hard to predict what kind of ideas will eventually end up succeeding in the marketplace of research.

**Joel Lehman:**
I try to come up with ideas in research that will be evergreen might not depend on the specific technologies like the novelty search ideas that we're pursuing in my Ph.D. or with really tiny neural networks, there was with neural networks that are 10 neurons or something that you connect.

**Kanjun Qiu:**
Wow.

**Joel Lehman:**
Yeah. So really different scale than the things we care about today.

**Kanjun Qiu:**
Yeah.

**Joel Lehman:**
But the philosophy behind novelty search is still relevant to the field of say at deep reinforcement learning, where it and similar ideas have been really impactful. The exploration in reinforcement learning is a really difficult problem, no matter whether you're dealing with small neural networks or big neural networks. And so those ideas still are evergreen. I think also because I tend to try to be drawn towards algorithms that have some kind of philosophical insight, not just an insight that's maybe specific to a particular implementation.

**Kanjun Qiu:**
What do you mean philosophical insight? How do you know the difference?

**Joel Lehman:**
It's subtle because lots of research papers you read will have some kind of insight or they'll oppose what they have as an insight in the sense that they could actually impact your life, maybe. So, that would be one really strong criterion. So I do think that novelty search has a grain of philosophical insight in it that is not even just about machine learning. A lot of the things I've been interested in, whether it's novelty search or the kind of the broader field of open-endedness or AI safety, is the way that discoveries about those algorithms might also relate to broader things, like research in general, life in general, or the trajectory of society in general. I think there's all these interesting, interlinking parts. Part of this is the attitude I think. These days I think that I'm interested in machine learning almost as much about the kind of philosophical worldview, understanding the world kind of aspect as much as it is about just the excitement about open-endedness, how cool it would be to have an open-ended machine learning process and how useful that could be.

**Josh Albrecht:**
What do you mean exactly when you say open-endedness?

**Joel Lehman:**
I think the easiest way to talk about open-endedness is to kind of point to some processes that we're familiar with that are open-ended, like biological evolution for example. As an algorithm that's run for billions of years in one run of biological evolution has produced all the amazing diversity of life, including ourselves. It's amazing that volitionless process produced volition. That's just sort of insane when you think about it. We are collections of self-replicating at times, robots that ourselves, that somehow the selection of robots, these cells leads to the experience of subjective experience of consciousness. And it's just mind blowing that this is all the product of this billions-year long process of continual innovations. If I really think about it, I still am kind of blown away by the majesty of biological evolution. So that's kind of what I mean by open-ended. So it's kind of continuing to create new things, diverse things over time.

**Joel Lehman:**
Another process we're familiar with is human innovation. So art and science, or doing is for creating new knowledge. And oftentimes when we discover some piece of knowledge, it actually invites more questions. So it actually invites us to look to create more science and actually some fields of research will respond new sub-fields and sciences as a whole. So far it doesn't seem like it has a natural stopping point. So it's gone on for a thousand years or something, and then true informal science started.

**Joel Lehman:**
But it doesn't seem to have a stopping point. If anything, it's growing and expanding and diversifying. The grand ambition of open-endedness would be to create within a computer, an autonomous search process that demonstrates qualitatively similar behavior. You could run it for a billion years and it would keep surprising you. We don't really have algorithms that you run for a billion years and they would do that. Usually a machine learning algorithm starts from a fixed start point and has some fixed objective and once you reach that objective, there's not really much use in running it any longer.

**Josh Albrecht:**
I sort of assumed that we did have algorithms like that, they were just kind of, maybe the computational bounds meant that the things wouldn't be that interesting that fast or take a really long time or something like that. You can almost imagine making random neural network architectures, right, if you were sufficiently exhausted about the way in which they were randomly linked. Yeah, you would eventually create every single art, but it would take longer than the whole universe that sort of stuff. Sure. We'd eventually get there. It's just sort of way too slow maybe right now.

**Joel Lehman:**
There's a truth there, which is exhaustive search can eventually get you anywhere. And there's the practical constraints on that, like you wouldn't actually get there. But what is it about biological evolution and what is it about science or technology, these innovative processes that drives them? And so looking at an undriven process, doesn't really get to that question. In effect it's not going to be practical to do that.

**Josh Albrecht:**
I think you're right. I think there's something more interesting in these other types of search. There is something driving them. I don't know what it is. Maybe you have some ideas about what that is.

**Joel Lehman:**
Yeah that's a really important, powerful, deep, and maybe not well understood question. There is a question about biological evolution, which is how important is just the genetic drift, which is kin to kind of random selection, subject to some constraints. Drift I would describe as random changes that aren't guided by anything or as exploration would be changes that are motivated to get someplace new. For example, if you were going to explore a room, you could do so by just sort of randomly shuffling around, or you could sort of use some volition, say how we can see that if I went there, I learned something.

**Kanjun Qiu:**
I have this extremely non rigorous, so caveat model of science and creativity, they feel very similar in some way, as like there are these two different processes happening. One is dripped where you're exploring things and playing around without any idea of what you're going to get out of it. And you're just doing it because it's enjoyable. There's like something else that is driving this, that is not the goal of where I might go.

**Josh Albrecht:**
Sounds like randomly dancing around the room. We're having fun dancing.

**Kanjun Qiu:**
Randomly dancing around the room.

**Josh Albrecht:**
You will explore the room also as a side effect.

**Kanjun Qiu:**
Right. In intellectual space that's kind of like thinking about something because it's interesting. You don't know if there's anything there or you're exploring. I've always thought about exploration as not being particularly goal-directed.

**Joel Lehman:**
So it's true that there's kind of like this nuanced distinction maybe between drift and exploration and kind of goal-seeking behavior. When we think about goal-directed behavior, we have something specific in mind that we're moving towards like an objective that we want to reach. So more or less, we might have tunnel vision around that, like I need to get there, what are the steps that seem most obvious to get there?

**Joel Lehman:**
Random drift might be just doing something without any motivation. I think actually play is a motivation. So if you have no motivation, there's lots of things you could do that probably wouldn't be that informative, not really just sitting on the floor and sort of just moving your limbs around randomly. So that would be drift maybe to the most extreme. You can dial that in.

**Joel Lehman:**
While I wouldn't say that exploration need be goal-directed in this sort of seeking an objective sense, you are often doing things that either explicitly or implicitly will give you information or that are driven by information.

**Kanjun Qiu:**
Yeah, that makes sense.

**Joel Lehman:**
Like novelty search, there is a signal about doing something different than what you've done in the past that is likely to generate some kind of information, whereas genetic drift might lead you to do exactly the same things over and over again.

**Kanjun Qiu:**
So if I were to characterize the difference between drift and exploration and goal-directed behavior, those three different things, goal-directed behavior is you know what the goal is and you're optimizing for it. Exploration is actually a process where there is an implicit goal of seeking more information. It's much more general because this information can be anywhere, so play is a mechanism for seeking information. But drift is actually quite random. It is not an information-seeking process.

**Joel Lehman:**
Yeah. And so, it could be that the way that I'm laying these categories out is a little bit of kind of a straw man, but that's how I would see it. One interesting facet to this that I think is also maybe a little bit underappreciated is we talk about reinforcement learning, and there are mechanisms for exploration and there are incentives for exploration. So for example, an incentive for exploration might be novelty-seeking, there's a account-based exploration. There's a whole bunch of different kinds of exploration incentives, like a bonus you get, intrinsic motivation.

**Joel Lehman:**
But a lot of the times, the actual mechanism for exploration is really, really naive, and cue learning, you often use Epsilon-Greedy exploration as the implementation, like how you actually might encounter new states is you take random actions. Or in a policy gradients methods, you might have an entropy bonus, which is just increasing your chance of taking random actions. You get some intrinsic reward just for being a little more stochastic. You might have a very sophisticated incentive and yet have a very kind of naive mechanism.

**Josh Albrecht:**
It seems like your paper, the Go-Explore, that sort of paper is related to this and that that may be a better actual mechanism for exploration.

**Joel Lehman:**
Yeah. So the insight in go-Explore is to first return then explore. In other words, if you have an idea of an interesting place to explore from, so in the RL, it's going to like an interesting state, do you think there's potential in this state that could lead to interesting new things? The key would be to first get back there. When you're getting back to a state, you don't want to be using any of your mechanisms for exploration necessarily like the Epsilon-Greedy or the entropy in your policy. But once you get there, then you could use any kind of mechanism to explore. And ideally, you would have a more sophisticated mechanism than Epsilon-Greedy or an entropy bonus.

**Josh Albrecht:**
Can you talk a little bit about where the paper came from and how it got started and what were some of the initial ideas and kind of the story behind it?

**Joel Lehman:**
Yeah, I think that paper does have a long history. The longest history is that it relates to this field of what's called quality diversity, which is kind of arose in evolutionary computation. Quality diversity is about how do you create a wide diversity of things that each are locally as good as they can be?

**Joel Lehman:**
You can imagine if you were trying to mimic biological evolution, there are lots of different scales of fitness. A bacteria replicates in minutes, a bear replicates in years. It takes years, I imagine. If they were to compete directly in terms of fitness, then we would have a world dominated by bacteria.

**Joel Lehman:**
But that's not how biological evolution works, there are different niches where you can make a living, the way that you make that living might be a different scale of fitness. So bacteria competes with other bacteria, bears compete with other bears and kind of predators of bears, and so on.

**Joel Lehman:**
You might want to have an algorithm that has the same quality where it's going to find solutions that can be very, very different from one another that have the best version of that that you can imagine. If you're evolving virtual creatures, you might say, "I want to see the best quadruped and the best biped, the best tall creature, the best small creature. That field of quality diversity kind of branched from this algorithm called novelty search with local competition. That, I think, is sort of like the seed of the idea.

**Joel Lehman:**
The more practical seed of that idea, I think, came from Jeff Clune and Joost Huizinga. Jeff was a professor at University of Wyoming. Joost was his PhD student. There's kind of the idea of we'll use same ideas of quality diversity to help solve hard exploration problems in RL. In RL, you might want to explore all these different states, like an evolution computation where you're trying to find different creatures that demonstrate different kinds of behaviors and be locally good. And the analogy [crosstalk 00:25:10] is can you find trajectories that lead to different states and where these trajectories will get different amounts of reward? You want to find as many different good trajectories as possible that are maximally different, and that could be a good way to solve hard exploration problems.

**Joel Lehman:**
I think the algorithm is kind of further developed at Uber AI. I think initially we were interested in what you might call a repertoire. So one thing that quality diversity algorithms have been used for is you create a lot of different ways to solve a problem. And then, depending on the context when you're deploying it, what the actual problem is, you can just apply the thing that you learned.

**Joel Lehman:**
I think the hope of the project was to try to integrate all those other sub-policies. So you can take a conditional policy that if you wanted to go left, it could go left. You want to go right, it could go right. And there could be some synergy from a policy learning all these sub-behaviors. I think at that point, it didn't really have much to do with hard exploration, then somehow applying that algorithm to Montezuma's Revenge, somehow that led to us pivoting.

**Joel Lehman:**
One of the key pivots was that we were thinking that we'd be learning all these different neural network policies, but it turned out, we just learned raw trajectories. We created this Go-Explore algorithm that had two phases, and it turned out that the first phase didn't involve any neural networks at all. It was just kind of going through as a deterministic simulator and just finding all the different pathways to get high reward, just memorizing the trajectories. And later, in stage two, you would actually use a neural network to kind of integrate all that information together. In our initial thinking, we'd say, "Oh, there'd be a neural network involved in all the stages."

**Kanjun Qiu:**
You started in this kind of evolutionary algorithms, neuro evolution for a very long time. Then deep learning happened, and now you're doing a lot of reinforcement learning. Why reinforcement learning? Why choose that in particular?

**Joel Lehman:**
I've always been interested in reinforcement learning like problems. Novelty search was using a form of evolutionary RL, using evolution to evolve the weights of a neural network that would get high reward, high fitness on some simulated task. I was always interested in RL, but that transition from evolution to deep learning was interesting because I was so skeptical of deep learning for probably too long a time. But now, I'd say I'm kind of very agnostic.

**Joel Lehman:**
I think evolution does have some role to play, and it could have an outside role in the future. It's unclear. But it's clear that deep learning is just massively powerful, and it does seem like the reinforcement learning framework is a natural framework for something like open-endedness, whether it's evolution or RL that's the kind of the formal framework for the current technology we're using, isn't ultimately that important to me, I think.

**Kanjun Qiu:**
You think RL is a natural solution to open-endedness. My conception has always been that RL is a little bit too objective-focused.

**Joel Lehman:**
Yeah. It always gets a little confusing when you're talking about formalisms and how you can kind of wrap one idea into another. And I definitely can agree that most applications of RL are very goal-oriented. This is one objective function you're trying to measure, but it can be enfolded into an open-ended process.

**Joel Lehman:**
I can point to an example of a paper that could demonstrate this, a paper called Poet. Poet seeks to create challenges for itself to solve. A key element of open-endedness is this theory about stepping stones, that to get to a really ambitious place, you need to kind of assemble a wide array of stepping stones through exploring one stepping stone and seeing what the potential of that stepping stone is to lead, so where achieving one local goal could lead. You might eventually step your way more and more broadly into the space of possibilities until you actually maybe can reach the goal that you cared about in the beginning.

**Joel Lehman:**
And so, Poet is first starting out by inventing really simple problems for itself that it can solve basically with RL from very humble beginnings like a [inaudible 00:28:55] neural network. Poet deals with controlling little biped walkers that can traverse a terrain. The objective would be to have a walker that makes it all the way through this terrain. And the terrain could have obstacles in it, could be more or less rough or wavy.

**Joel Lehman:**
And the idea is that you can use RL to solve one of those local problems, and you could use both that problem that maybe initially started with a very flat terrain that's easy to traverse. That problem could be perturbed to generate a more difficult barrier to that problem. And you could use the behavior that solved the simple terrain as a stepping stone to solve this more complicated terrain. It's like using RL locally, but it's embedded within a process that is more open-ended.

**Kanjun Qiu:**
You said you were a deep learning skeptic for a long time. What happened?

**Joel Lehman:**
I think that I had a straw impression of what reinforcement learning was. For example, I think when I was coming through grad school, there was kind of an opinion, at least within the evolutionary computation world, that continuous action spaces or really large state spaces were something that RL struggled with. There was a time where using function approximators for state and representation wasn't that popular or it wasn't working that well. I guess it was hard at the time to see the ultimate potential that the paradigm had.

**Joel Lehman:**
And then, even as the results were coming out, I think there was always a kind of yes, but-ism, where it's like, okay, so yeah, it can solve Atari, but can it do this or that? At some point, I guess the evidence just becomes too much, and the firmness of your belief crumbles. And there's a sort of disorientation that can happen there, but also it's useful and productive.

**Joel Lehman:**
I think there's an outside shot that something like an evolutionary algorithm will be really key to AGI, and I think probably have more probability on that than a lot of people would have. But also it's not that big of a probability at this moment, so I think it has to be critical.

**Joel Lehman:**
The case that it feels strongest to me is something like Jeff Clune has a paper called AIGAs, AI Generating Algorithms. It involves kind of making a case for that. Right now, one paradigm of AI is trying to have researchers individually research and combine all the building blocks that we need to get something like AGI. So you research, here's [inaudible 00:31:04], here's a transformer, we need batch norm here and so on. And you're kind of learning lessons about these different building blocks, how to put them together.

**Joel Lehman:**
And it involves a lot of research effort, but it does work really well. The GPT-3 is ultimately a simple-ish architecture. It's transformers all the way down, and it works amazingly well. Nothing knocking against that paradigm, but there's a different paradigm. You could view it as a higher leverage paradigm, if it works. It's much more ambitious. Well, the aims of machine learning would be to automate everything if we could. Can you have an algorithm that basically does its own R&D, that it creates building blocks, it assembles them together? And you might say that sounds a little ambitious. Well, it is. There's two reasons I think it could work.

**Joel Lehman:**
One is that it's basically automating what the machine learning community is already trying to do. So it's like if we can do it, there's nothing that means a computer couldn't do it. Maybe more directly, biological evolution basically did it. And that's really, it still is kind of mind blowing that basically it automated and explored its own research and development program into intelligence. It's really interesting to think about from that perspective that it explored so many different paradigms of adaptive behavior, plants and bacteria and animals and different ways to organize animals, insects, and mammals, and birds and reptiles, and only one branch did that lead to AGI.

**Joel Lehman:**
So you could think of it, it was basically doing basic research, and one branch kind of paid off from the view of AGI. It seems like it has to be relatively simple algorithmically because it is just the unfolding of natural law and can't be that algorithmically complex, yet seemingly we still haven't really cracked the case on that. That's one of the reasons why I think that open-endedness is so profound is how is it that it's so difficult for us to formulate this kind of learning problem and create an algorithm that could at least match the efficiency of biological evolution in terms of creating this kind of open-ended process?

**Joel Lehman:**
Now, biological evolution isn't that efficient. It took billions of years and who knows how much computation, if we wanted to simulate that all out. So it's not saying that it's necessarily the most efficient route to AGI, but it's very thought-provoking. If we crack the insight into what makes that a simple algorithm, if we could port that insight into something like RL that is more sample efficient, then maybe this kind of paradigm could work, you could actually automate the entire process of research. Now, it's definitely an ambitious undertaking and who knows if that will work? But it seems, at least, kind of like an outside chance of maybe working.

**Kanjun Qiu:**
Well, if you're imagining, "Oh, evolutionary algorithm might lead to AGI," which is simulate everything, simulate a giant multi-agent universe of all of these different types of creatures that hopefully evolve intelligence, which seems very computationally expensive, that's the maybe naive imagination of what it might look like to use evolutionary approach toward AGI. What's your imagination of what an efficient evolutionary approach toward AGI would look like?

**Joel Lehman:**
Historically, how the open-endedness community has tackled this is maybe there are a couple of different prongs of research that people pursue. An approach that is popular within the field of artificial life, so artificial life is about how do we create life in a different medium than cells and flesh and biology that might involve creating a world like you're suggesting that is just some basic physics? Maybe you seed it with a self-replicating creature organism, and then you just hope that the dynamics of that will unfurl and you get something really impressive. From the perspective of efficiency that you were saying, it seems like a stretch. It would require a whole lot of computation to then make evolution on that scale.

**Joel Lehman:**
Then another thread of open-ended research is trying to come up with the solution to this analogy problem. So imagine this SAT analogy problem, which is bird is to jet as evolution is to open-endedness. Humans, at some point, might have been inspired by birds. That bird's flight is really interesting, it shows it's possible to fly. And then, we even tried to mimic that with ornithopters and those kinds of machines. But the history of flight took off when we had some hypothesis about what are the core principles of flight that enable us to engineer things that could more efficiently do things maybe that weren't even possible for biology? You can't create a bird that carries tons and tons of cargo across the ocean.

**Joel Lehman:**
Similarly, while we might take inspiration from biological evolution, what are the core principles of open-ended creativity? If you could bottle creativity into a jar, into an algorithm that could efficiently instantiate an open-ended process maybe that is aimed towards whatever domain we want that could do so really efficiently and in a way that's not like biological evolution, but actually has maybe capabilities that are much more impressive than biological evolution.

**Joel Lehman:**
So I think that's describing abstractly the aim of this other thread, which would be to actually understand at a deep level the principles. And then, if we had those principles, then that would drive things. The question would be what are those principles? And that's an active question, maybe the stepping stone principle, when an algorithm that recognizes things for their own merit, as in trying to preordain where they will lead to.

**Joel Lehman:**
A minimal criteria has come up as a stepping stone a couple of times in the open-endedness literature. A search process that seeks many different ways to do the same thing can be a powerful search process. So you could reframe biological evolution as a search process that is searching for many different ways to survive and reproduce.

**Kanjun Qiu:**
The minimal criteria of evolution would be survive and reproduce.

**Joel Lehman:**
Yeah. If the minimum criteria of biological evolution is to survive and reproduce, then you unleash a search process that is trying to create things that meet that minimal criteria in a different way. That can result in a really interesting search that has more of a flavor of Rube Goldberg kind of device creation, but of engineering towards a particular purpose. I guess I more and more view biological evolution that way as opposed to just a directed invention process.

**Kanjun Qiu:**
It certainly seems knowing biologists and how frustrated they are with our machinery that we do appear to be Rube Goldberg machine.

**Joel Lehman:**
Yeah. There's definitely these digital organs and vestiges of evolution in general that are with us that are strange. I guess the birth process, the difference between how wide our head is, and it makes birth more dangerous than we'd like.

**Kanjun Qiu:**
Related to open-endedness and what you were just talking about, what do you think is the most interesting work that's happening right now in open-endedness?

**Joel Lehman:**
I mean, there's a lot of interesting stuff going on. It's hard for me to kind of point to one thing in particular. I think I'm excited by interest that people are having in open-endedness. And maybe one thing that I point to as a general theme that I'm excited about is how ideas in open-endedness have been around for a while that maybe originated in the evolutionary world are now becoming more relevant to mainstream machine learning. And just the powerful machinery of deep learning, it's exciting to kind of see how that let's open-endedness be more efficient and better reach its aspiration.

**Josh Albrecht:**
This whole idea of AI making AI sort of a thing, that kind of approach, stimulating life, or you can have this other sort of approach, which is the jet engine version of evolution for going and finding and doing search in order find these, instead of having people do this. What does this look like philosophically, if that makes sense? It seems like it's typically what this looks like is some of the network architecture search papers maybe that you worked on a little bit recently or maybe some other ideas. How do you think about that?

**Joel Lehman:**
When you think about a system that would basically do AI research, that's an aspiration you have, you could say that architecture search is an important component of that, whatever the substrate of this AI is will be of neural networks. And that seems like a pretty fair assumption. Beyond architecture search, there's also the element of creating challenges and solving challenges, so what is the architecture search applied towards? And you probably want that to be integrated in this overarching open-ended search process, so that architecture search, tasks.

**Joel Lehman:**
I would point people who are interested in this question to Jeff Clune's AIGAs paper, a little more depth than I can manage off the top of my head. The jet engine kind of approach to evolution is going to be driven by hypotheses about what enables biological evolution to work. Hypothesis about the general creative principles underneath biological evolution.

**Joel Lehman:**
So on one level, it's going to be about architecture search and problem creation and solution and so on. Another level is going to be driven by what do we think are the principles, the philosophical principles that enable open-ended creativity across domains? So I guess both of those levels are important. To me at least, seems like the philosophical insight is more important than how you end up implementing it. The implementation, I think, will feed from that.

**Joel Lehman:**
It also just reflects, I guess, how I approach research, which other people might have a more hands-on approach where they are entangled with a problem first and trying to figure out how to solve that more directly based from AI. I really like to have an idea of what do I have that I could test out in an algorithm, but it's driven by my feeling that I understand the problem more deeply now.

**Josh Albrecht:**
Can you speak to these philosophical ideas, [inaudible 00:39:46], behind two of those recent network architecture search papers then, the generative teaching networks and the synthetic Petri dish?

**Joel Lehman:**
It's actually a hypothesis about how science works. That's how actually I see the synthetic Petri dish. And so, the synthetic Petri dish is a paper where you are trying to learn how to create a Petri dish, which is going to be a set of input-output patterns that you test on the small scale. It's a paper in the network architecture search space. You're trying to find a big architecture that's going to do well on some big dataset. And you want to make progress on that by creating a little test tube environment, a Petri dish environment that's smaller, yet will reflect something about the bigger environment. The hypothesis in this is that what we want is to actually have in the Petri dish, some of the same gradient descent mechanisms embodied there as well. And that's actually going to help us to do basically virtual science. The Petri dish usually is some smaller ... It's instantiating this motif with gradient descent on this invented training data.

**Joel Lehman:**
You're trying to learn a training set for this motif, such that it will actually reflect the performance of the larger motif in the larger network. And you can use gradient descent in a clever way to align the performance of the Petri dish with the bigger network. It's one interesting thing that comes out of that is you can start to see that it's able to make predictions that seemingly would be difficult without actually embedding the mechanisms of gradient descent within that Petri dish.

**Joel Lehman:**
The way that the human science works is that we do this kind of Petri dish sort of thing. Literally with Petri dishes, we try to isolate some part of the system that we think is important that's going to actually reflect the bigger system. I think that's kind of the philosophical insight is that we want in some ways to embody an aspect of science within architecture search. Which is something that helps us when we're doing science to use our resources wisely. So what we do to these small scale experiments, often hopefully using the same elements of the system. Another approach would be just using the motif itself without embedding it in a gradient descent process, predict how well it's going to do when you put it in the bigger network. And the hope here is that by actually having the elements of the system itself, that actually using gradient descent in the motif and the Petri dish, that we can get further.

**Kanjun Qiu:**
How did you get to this [inaudible 00:41:58] insight? Did this people come out of, "Oh, I had this idea. We should embed science inside the process of science, inside this," in your architecture search?

**Joel Lehman:**
This was kind of like a lunch table discussion at Uber. I think Ken had the initial insight or something. And then he was like, "Would it be possible to do this?" And then that afternoon, I highlighted a diagram for how I thought we could actually implement it or something. I don't know if he was thinking about architecture search, and that kind of came to him, or what his thinking process was. My role in that paper was sort of, "Okay, here's an idea. And how is it that we can actually implement this with the mechanisms of machine learning?"

**Josh Albrecht:**
And then for the generative teaching networks, is there a sort of philosophical angle to that as well?

**Joel Lehman:**
I think Jeff and Ken had similar ideas simultaneously on that one. I think I can only remember exactly kind of the Ken thinking. It was inspired by GANs, in that GANs are generative adversarial networks. And the thinking was, "Well, what if we put them on the same team? So they're not adversarial networks, but they're cooperative networks."

**Kanjun Qiu:**
Interesting.

**Joel Lehman:**
So I think the original title was something like, Generative Cooperative Networks. But from there, I think just having that premise, you can kind of think of like, "Okay, how do we actually implement that? What would it actually mean? Is there something interesting there, exciting there?" And it ended up being a mechanism to learn a dataset ... In some ways it's similar-ish to the Petri dish, just like learning a synthetic dataset. But here for the hope of training a network more quickly, you have the full [inaudible 00:43:21] dataset, 60,000 examples or something like that. And you want instead to quickly see the promise of a new architecture. And you distill that dataset down to something smaller, artificial data points, a couple 100 examples that could quickly give you a sense of how good that architecture is. A lot of the dataset looked nonsensical. You create this artificial dataset that looks a little bit crazy.

**Kanjun Qiu:**
I love the idea of that [inaudible 00:43:43] of flipping from adversarial to cooperative. And then thinking about what that generates.

**Joel Lehman:**
That in itself is kind of demonstrating the value of play. In that, "Here's this ubiquitous idea. What if we flipped the idea of antagonism to cooperation? Does that lead to anything new?" I think it also leads just to the value of contrarian thinking in general. Yeah, a field like deep learning where the field is exploding, and everyone is entering the field and pursuing the most obvious ideas. How do you make a living? How do you do impactful work? It's really difficult.

**Joel Lehman:**
And I think it requires almost a philosophy of research, so you understand what it means to make an impact. Either it's finding your own niche, or it's developing intuitions where you strongly diverge from the field and just sticking to that, and exploring that. So it's often risky, because if you're going outside the norms of the field, then if it doesn't work out, then you're left with not much. Whereas if you're kind of going along in the most obvious directions, and you get a half a percent point increase on a benchmark, then probably you can still publish it. And because it's fitting all the narratives that exist in the field, reviewers might be very friendly to it.

**Josh Albrecht:**
We were just talking about the generative teaching network and the Petri dish network. And there's both sort of ways of making more efficient network architecture search, right? But there are other ways too. You can make models that predict how well other models will do when they train. Or you can imagine training and over-fitting to just a really small number of data example. Or there's probably a really large space of possibilities there. But maybe there isn't.

**Josh Albrecht:**
And so I just kind of wanted to get your thoughts on how do you actually explore this whole space of models? Isn't really just, there's a very small number of ways in which you can think about how to predict them? You either have the choice of training the whole model, or you have a choice of making a prediction. In which case, your prediction can only really vary in certain ways. Maybe you can only make it smaller or not as wide, or not as deep, or not as many training examples. And those are kind of the only options. Does this seem like a really big space of potential things you could do to estimate, or to make more efficient predictions for network architecture search? Is there a whole bunch of possibility there or not?

**Joel Lehman:**
So I think there is a pretty broad space of possibilities there. Because I think there are a couple entangled factors there. One is the expressiveness of your architecture encoding, if that make sense. So you could imagine constrained space of architectures, which is maybe you kind of look for the best ResNet or something. And you have different parameters you can kind of tweak there. You could also imagine going to a very, very expressive encoding for architectures, which might be writing raw TensorFlow codes. You actually want a machine that will write TensorFlow code or something like that, or manipulate a computation graph in a really granular way. And so that's just the space of encodings. But it does relate some way it's entangled with the kinds of predictions you make. Like you said, there's also the aim of your architecture search, whether it's to find a more efficient network, or whether it's defined a new paradigm of model, or something like that.

**Joel Lehman:**
I do think that prediction is one key element. So you have some heuristic that you think is going to be indicative of performance. That could be a smaller model, that could be limited range of training, a scaled down version of the model. A lot of research in neural architecture search right now makes a particular hypothesis about that. Like [inaudible 00:46:51] one facet of that. And ideally, we might want an algorithm that could learn more of that itself. And that's also kind of an ambitious direction of research. So I think it is both constrained and very free. Constrained in the sense that I think the practical approaches that we pursue in the short term are relatively constrained. Prediction is one key element there. Both the generative teaching networks and the Petri dish highlight that there still is room for creativity there.

**Joel Lehman:**
Generative teaching networks, you could view it as something that's about creating more efficient training paradigms. So I think it's also just kind of a lark in how far can you stretch this paradigm of just back-propping through everything and learning training data. And one of the more interesting facets of that paper is about kind of the future directions and speculations.

**Joel Lehman:**
Interesting considerations about what these generative teaching networks would mean for RL, for reinforcement learning. Could you actually learn an RL domain? A lot of the discussion there was kind of motivated by Jeff Clune who was thinking that it would be really cool to have a system that you just invent its own domains. What would it mean to have a really expressive neural network that could encode a full MDP, and learn within it? And would that make any sense? It's hard to know if it would make any sense. If at very least, there's a lot of open research questions in there. If you had a really expansive neural network that could almost encode any domain, could an algorithm start inventing new video games, new training scenarios, new robotic simulators, or something like that?

**Josh Albrecht:**
Yeah. That's exactly what I was hoping for, for the answer. Thanks. In one sense, it seems kind of restricted. All you can really do is predict the performance of the thing, and that's it. But actually there are all these other clever ways of generating the dataset. Or you can back up even further. You could do the whole training example, you can go even further than that. Like, "Which components are you selecting in the thing? There's the whole thing." Yeah, exactly. So I think that's a really interesting way of thinking about it. Thanks.

**Joel Lehman:**
Architecture search, it's been around for a while. But in some sense it's still a nascent field in that there hasn't been, I think, a result yet that has really moved the field forward in the way that the transition from COVNETs ... Sorry, from MLPs to COVNETs, or from COVNETs to transformers. We haven't seen yet an invention of something like that's wholesale new. I think that'd be a really exciting mark of significant for the [inaudible 00:48:55].

**Josh Albrecht:**
Do you have a feeling of why that is? And one thing that comes to mind is different neural architecture search, different heuristics work well for different architectures. And so it's very problem specific. And there isn't this general rule, and it's more like, "Well, if you're doing image classification things, these are some heuristics that kind of work with these models. But we can't say anything in general. Even the space is just sort of too big for us to really say anything about." Or I don't know, kind of your thoughts on that.

**Joel Lehman:**
I think my basic thought on that is that a lot of the algorithms, the search algorithms that are searching through the space of architectures are relatively greedy and objective driven. When we think about how key architectures that we now appreciate fully, developed themselves. It's not through this really greedy approach. Usually it took some time for us to appreciate MLPs actually being able to work at large scale. Convolution was impactful, maybe even when it came up. But it wasn't nearly as impactful as it was later. The elements of attention that later were developed into Transformer, they've been around for a while. But it was kind of unclear that they wouldn't be as impactful as they would be. So I think because architecture search itself is generally narrowly focused, it's not really well-suited yet to do the kind of basic research that maybe would lead to an architecture that really would be a really profound way. That'd be at least my hypothesis. Other people might have other opinions on it.

**Josh Albrecht:**
That's really interesting. You sort of want novelty search to go and collect a bunch of new components in architect [inaudible 00:50:23], and think about all of that.

**Joel Lehman:**
That'd be definitely a direction that I would be excited about. It's delicate to create the right encoding of architecture space. What's the sweet spot between really narrow thing where there's probably nothing creative to discover, or raw computation graphs where it may be very difficult if you get started there?

**Josh Albrecht:**
Expensive.

**Kanjun Qiu:**
Yeah.

**Josh Albrecht:**
So earlier you were talking about being contrarian, and the importance of that, and the difficulty of it. What work of yours do you feel like was most overlooked?

**Joel Lehman:**
First of all, I do think that contrarianism and a finely tuned contrarianism is really important. So I think it's easy to be kind of wildly contrarian. It's easy to be wildly following the pack. But to have a finely tuned sense of intuitions that you are willing to stake a bet on, and that maybe have some reason to think that everyone else is doing it wrong, I think are useful. And as far as work that I wish had been more impactful, I'm drawn to this paper that Ken and I had, I don't know, maybe eight, 10 years ago. It was about open-endedness. And it was called Beyond Open-Endedness, Quantifying Impressiveness had this, I think, unintentionally sing-song title. And it was about how it may be that open-endedness is actually kind of an orthogonal dimension from things that we would appreciate as being impressive. To make that more concrete, you can imagine getting really, really good at moving your left big toe in all sorts of intricate ways.

**Joel Lehman:**
And that open-ended exploration, if you could really get into that, you could really go deep into that. But if you show that to somebody else, they'd be like, "Cool. Okay. Yeah, you're really good with your toe. That's great." And it would be hard to appreciate what was actually interesting there, what was actually impressive about that. So in this paper we're talking about that maybe open-endedness isn't the right aim in itself. That's not the end goal really. It might be interesting to know how to do open-endedness. But that might not be just the aim in itself, because there are examples of artificial life systems. Where you create a virtual world, you put things in them. And it's really hard to judge what's happened. The actually impressive, it's hard to say. Like, "The little creatures did this and that. But how should I, who didn't grow up in this artificial physics, contextualize what they're doing? Is it actually ... Is it cool? Is it not? I don't know."

**Joel Lehman:**
We were hypothesizing that what you might need is actually a measure of impressiveness, or a kind of a theory of what makes something impressive. And what we came up with was that impressiveness is that an artifact, it should be easily appreciable how much design effort went into it. It's easier to appreciate someone doing a back flip than to do a back flip. It's easier to judge a novel as a work of art rather than to write a novel yourself. There's the same asymmetry between the appreciation and creation. It has vague sort of relationship to MP completeness, that some problems are really difficult to solve. Verification that the solution is correct is actually much easier.

**Joel Lehman:**
We used it as a trial domain, as images. This very subjective demand, just trying to create impressive images. What would it mean to try to ground that out objectively? We created this sort of artificial observer that would map an image to some set of features. Today we might have used something like an ImageNet network that could distill an image into meaningful high-level features. But we just hand coded a couple of them. Like, "How symmetric is this image? How compressible is this image by algorithm X, or by algorithm Y? What's the average pixel level?" And then we tried to evolve images using novelty search that would kind of span the space of properties. So it creates images that had all these different trade-offs. So now we have all these images that the system has created. Can we objectively measure how hard, how difficult it was to hit these trade-offs? So the idea is the high level features are sort of the broadcastable signs, something that actually would be apparent to an observer about the image.

**Joel Lehman:**
And we could say that actually this trade-off is very rare. So if we just generated random images, you would never see something with this signature. And also we tried to kind of get there from scratch to optimize from scratch towards that space, would that be hard to get to? It's kind of a proxy, another kind of thought experiment basically about, can we try to grind out this really subjective domain? My favorite papers I think that I've written actually is something that I feel drawn at some point to revisit. Because I do think it's an important insight that we want somehow to create impressive things. And if we had a theory of that, and we could quantify it, maybe we could optimize towards it.

**Josh Albrecht:**
I agree. I find that really interesting. Thanks for sharing that.

**Kanjun Qiu:**
This actually reminds me a lot of Paul Graham's essay, The Bus Ticket Theory of Genius. He says like, "To do great work, you need obsessive interest." My interpretation of his essay is basically, many people have obsessive interests in collecting random things that don't seem impressive on your scale of impressiveness. Like bus tickets. They collect many bus tickets. And you look at this collection of bus tickets and you're like, "Okay." It's like moving your big toe. And there are other people who get really obsessed on something that does seem to be actually really oppressive. After they got really deep here, someone else looking in from the outside is like, "Wow, there's a lot of complexity or new information here," or something like that. Information density is high. Whereas they look at the bus ticket collection and they're like, "This is not that interesting." I do feel like you were pointing at something that I see a lot, and I'm not quite sure how to figure out what the access actually is. But it's very interesting.

**Joel Lehman:**
I think I've read that essay one time, and I really enjoyed it. And I appreciate your description of it. There's also this other challenging aspect of it. Which I think you're kind of pointing out, where it's is this bus tickets or is this something important? And there's this phenomenon of artists that aren't appreciated during their time.

**Kanjun Qiu:**
Right.

**Joel Lehman:**
But later, it's impactful.

**Kanjun Qiu:**
Right.

**Joel Lehman:**
So there's this element of the difficulty of knowing at the time whether something is important or not.

**Kanjun Qiu:**
Yeah.

**Joel Lehman:**
A lot of people will have superficial takes on that. In some fields you need to have that kind of superficial take. So if you're running a business and you want to make a profit, then you can't spend 20 years wiggling your toe. But in the field of basic research, maybe we don't know yet what really esoteric fields of math will later generate really meaningful, useful things for us. What I would be most excited about in the space of open-endedness is not necessarily something that would inherently say, "This is bus tickets or not. This is boring as wiggling your toe. This is exciting." But at least it could tell you how to appreciate the artifact that it created. Like, "Oh, actually if you try to wiggle your toes like this, it would be really hard. Because there's this really complicated figure eight pattern. And the human toe is not designed to do that." And it's really impressive if only you cared about that.

**Kanjun Qiu:**
Like amount of work required as a way to think about impressiveness.

**Joel Lehman:**
Yeah. And if you want it to, you can even make this weird connection to cryptocurrency. And that proof of work or something is an important part of the blockchain. So at this point [inaudible 00:57:01] a step too far. But there's all sorts ... You can make any kind of connection you want, but it doesn't mean that proof of work is a useful mode of encouraging productive flavor, I guess. It's like the proof of work of a research paper. You don't want a research paper that's too trivial.

**Kanjun Qiu:**
Are there any papers or other people's work that you felt really impacted you? You spent a lot of time digesting it, changed how you thought about some things, maybe you built on it?

**Joel Lehman:**
Definitely I've been influenced by a lot of work. And strangely I think the most influential things tend to be things outside my field. The key insight to another one of my favorite papers is called Novelty Search with Local Competition. Just kind of a version of novelty search that kind of flipped something on its head a little bit, was deeply inspired by I think reading Richard Dawkins. It's either the selfish gene or the extended phenotype. There is a way where he presents the single-cell bottleneck, which is the idea that every organism, one feature that unifies all living organisms is that they go through this single-cell bottleneck when they reproduce.

**Joel Lehman:**
We might think of a single cell as a vehicle to make a human. But you could also say, see a single cell as a vehicle to make another single-cell. We're a digression from the actual process of interest. And there's also a quote, I think that is in our book from I think, Saul Spiegelman. It's something like, "Cells invented man to reproduce even on the Moon," or something like that. It's kind of a weird quote, but it's kind of once you have this mind expanding quality like, "Okay, evolution may not care about humanity per se. But from the genes I view, we are simply vehicles from our genes."

**Kanjun Qiu:**
How did that influence your paper?

**Joel Lehman:**
At that time when I was doing research, there might be a couple of core problems that I was kind of thinking about. So that paper was about how do we merge the pressure to optimize with the pressure to diversify in a principled way? One that might even put the pressure to diversify as the first order citizen, and the optimization pressure [inaudible 00:58:56] that. As opposed to the other way around, which now people have been thinking about it. That was a core problem I was thinking about. And there just felt something weird in how other people were writing papers about it at the time.

**Joel Lehman:**
I just had this feeling of like, "Okay, that's not right. There's got to be a right way to do this." I just read really deeply into other fields, evolution biology. That's why I was reading Richard Dawkins. Trying to get a sense of like what's actually going on in nature. And not going to be on the mechanism by mechanism level, but on the big picture level. The challenge was that a lot of writers in evolutionary biology write more about the specifics, and aren't having this sort of zoomed out view.

**Joel Lehman:**
I was just reading a lot of stuff and letting it simmer in the background, I guess. At some point it just became clear, "Oh, we can have local competition." The things that are similar to each other should compete within each other. And we should actually allow an incubation process where everything gets developed for its own quality. This flowed out of this evolutionary biology reading I was doing. I felt like there was a lot of inspiration coming from there. I'm sure a lot of inspiration was also coming from other work in the field as well. But it's less clear exactly how those influences worked.

**Kanjun Qiu:**
In artificial intelligence, are there any papers that really influenced you? Or more recent papers that you felt like were really interesting?

**Joel Lehman:**
There was a line of research by Douglas Hofstadter who wrote this book, Gödel, Escher, Bach, I think it won some really prestigious award. I think less appreciated was his work on programs that demonstrated analogies in a deeper way than previous programs had done. And there's a series of these esoteric architectures. We might say esoteric now, it just strikes me as something that to this day, we don't have algorithms that solve these problems maybe as well as those things did back then. Analogical reasoning like ABB is to ABC, try to complete the other analogy. This really depth of thought about how analogical thinking was so core to what makes humans think. I really buy it on some level, but I find it inspiring in a sense that it feels like whatever that element is, we don't exactly have. Maybe we get it as a by-product in something like GPT-3, learning some of those things indirectly.

**Kanjun Qiu:**
Do you think that worn embeddings are not actually capturing analogical thinking like arithmetic on embeddings is not enough to do analogical thinking?

**Joel Lehman:**
You can make a distinction between thinking fast and slow. That's kind of like a rough distinction. The fast thinking of analogy might be that we already have these sort of embeddings of things in our minds and we say, Oh, King and queen, they differ in gender or something like that. Point to something else. We're very familiar with that. But I think with more esoteric analogies, Hofstadter goes through a list of things that actually require active search to figure out what would satisfy it. And when you think of these analogies, it's something like who is the Margaret Thatcher of the United States or something, or something where it's like... Think about what facet of this person I want to focus on, Hofstadter would argue, in translation as well. Like how do you actually translate the essence of a poem to another language?

**Joel Lehman:**
It's very difficult because the building blocks you have in one language are very different. And what do you want to transplant to get the spirit of that thing. But I don't think that worn embeddings are going to solve that kind of thing, because it actually feels like a search process. The felt sense of it, like the experiential sense of it for me, when you're trying to solve that kind of analogy, it's like, it kind of clicks. It feels like, Oh, that's a better answer than this one.

**Kanjun Qiu:**
Yeah like this feels more right.

**Joel Lehman:**
Yeah. It feels more right. Because there's some way in which it better satisfies whatever constraints you have in your mind. The thing that involves the active search, that's the part that still seems a little mysterious to me. That'd be maybe the more thinking slow part.

**Kanjun Qiu:**
I really like that way of thinking about it. Interesting. So you've been a researcher for a long time and migrated fields a little bit. What are some of the things you feel like you've learned in all of these years?

**Joel Lehman:**
Many things I'm sure. There'll be things from the tactical to the strategic and beyond. I guess what comes to mind first is just the psychological difficulties of research. It's a tough field. A lot of projects have this sort of arc where you have a good idea. Maybe it's initially working kind of well, very optimistic. And there's this trough of sadness-

**Kanjun Qiu:**
Trough of sadness.

**Joel Lehman:**
Where you just, you hit some kind of wall and things aren't working well, it's not clear if you're ever going to get out of it. I think there's this is deep uncertainty in research. The first time you go through that, you need a lot of coaching, at least I did. Because it's disheartening and it's hard to stay motivated when it seems like you really could be wrong. There really could be nothing here. Then having a good mentor who maybe believes in the idea a lot can be useful, of course the same mentor needs to also, or yourself needs to be well calibrated. Sometimes you have to give up too. It's just not going to work.

**Joel Lehman:**
After you've been through the process enough, where there is this trough of sadness, and sometimes, if it's a good idea and it really has legs to it, you get out of that and you actually make it to the other side of that and can publish it or find results that validate your hypothesis. When you've been through it a couple of times, then you can't get used to it a little bit. But it's still really hard. I think a common phenomenon for people that are doing probably research in general. But I know... I mean the machine learning researchers is just to feel bad when your algorithm isn't doing what you want it to do. It can feel really bad and you can just feel like, okay, everything is terrible. Even though maybe it will get better or it won't get better. It doesn't reflect that you're a bad person or something, but it can feel that way. Especially if you've invested a lot of your personal identity in success. And ideas really sometimes don't work. How do you deal with that psychologically? How can you mentor other people through that?

**Kanjun Qiu:**
How do you handle it for yourself now, if you're more resilient, what has led you to build the resilience? When do you know how to give up? When do you know to keep going? Do you have some felt sense for it? Do you have heuristics?

**Joel Lehman:**
It's kind of a lesson that I wish I'd learned earlier, but just having a full life. Like your life shouldn't be adjust research. And I think when I was a grad student, there was more intensity around getting results. And maybe you're feeling either explicit or implicit pressure from your peers, or from your advisor, or from the research field in general. Like how successful people are, people talk about these Twitter threads of people having 18 papers [inaudible 01:04:33] or something. And you're like, Oh, I'm so terrible. I only have one or I don't have any, or I got rejected and you just feel so terrible because of that, even though this is such an impossible standard for success.

**Joel Lehman:**
So just having other things in your life that are going, okay, so like friends, a relationship, hobbies, your family, whatever it is that brings you joy generally. Making sure that you're investing in that as well. And that's not always easy because being a grad student in particular, it can be a pressure cooker. Psychological wellbeing is important and taking care of yourself, even if you're viewing it through a cynical lens of you just want to be more productive. I think ultimately [inaudible 01:05:06] yourself will lead even by those that metric. But it's probably also more wholesome to think of it as I want to be happy while I'm doing something as well.

**Kanjun Qiu:**
For those people who are skeptical that taking care of yourself is a good thing. Do you feel like it has made you more productive as a researcher?

**Joel Lehman:**
There was a certain kind of maniacal single-mindedness I had when I first got into this field. And I guess I would say there wasn't an unbalance that I had probably in how I approached research when I was an early grad student. But also I was on fire for what I was doing. And so I think I was just really, really passionate about it. All things considered, my outlook on my life as a whole, as it could have been if I had balanced that more with friendship and a relationship with other things, it was really the life that I wanted to live at that point. And there was a lot of pressure I put on myself, but I think I enjoyed a lot of it.

**Joel Lehman:**
I think my productivity would have taken a hit had I not been so just passionately interested in what I was doing. It's probably nuanced, but do think in general, if you're trying to force yourself to do more work out of a sense of guilt or obligation, you can get burned out fairly quickly. And that will, even from the narrow lens of productivity that will just put you in a deep hole.

**Kanjun Qiu:**
How about other things you learned, even tactical things or more high level things?

**Joel Lehman:**
One of the tactical things I'm still learning is, despite how hypnotic it is to watch your loss curves go down. There's better ways to use your time. There's something just beautiful about watching the training run progress, and somehow it never goes away. The temptation just to micromanage your runs like, Ooh what's it doing? Maybe this is the run. So somehow I never have quite figured out self control there.

**Joel Lehman:**
I guess picking research problems that you think are impactful or that you care about has been kind of an ongoing learning process for me. So across the arc of my career, there was a period of time where I was really, really on fire for open-endedness. And then there was a time where that momentum kind of fell out for awhile. And I really wasn't as excited about it as I had been. I think I tried to force myself to care more about it. I sort of segwayed into a different research field. I worked on AI safety for a bit, and that was really refreshing. And I think the thing that I was really wanting was to have more confidence that what I was doing was actually helping the world in a positive direction. The search for meaning became more deep than just finding some kind of research discovery that I thought was cool, and that would gain me attention.

**Joel Lehman:**
But it shifts more towards, what is my legacy, at least the sense of, is the world a little bit better from being here or not? What is the impact of this? And that kind of led to this whole pigeonhole of thinking, like how could we ever know? Especially in the research world where what we are creating, especially with basic research is so far removed from the actual applications, it's so hard to know anything about that. And it felt to me that philosophical struggle I was having on the object level, like what field of research I go into, actually is something that is deeply related to the field of AI safety, which studies problems like that. Safe exploration, how do you create an RL agent that is going to explore its environment without causing catastrophic damage to itself? In some sense it analogical of the same problems we face in the real world.

**Joel Lehman:**
For whatever reason, I keep getting drawn into search problems that are analogous to the problem I feel like I'm actually facing in my life. I don't think I consciously decided to do that, but it just made be how my mind works. I just felt drawn to this direction. I still care a lot about AI safety. And that's part of the reason why I'm at Open AI as part of their mission. But also, I feel there's a way to resolve this, in that I'm really interested in open-ended systems that have some level of safety within them. And that's the basics of research, is thinking about the high level goals of basic research, I think it's to improve the world. And that might mean that this open ended system of research needs a little bit of control. And that's something that some research fields have already dealt with.

**Joel Lehman:**
So if you wanted to work in nuclear physics or something, some discoveries that you make, maybe won't be publishable or there's some mechanism for responsible disclosure of things that could lead to a new nuclear weapon. Or if you're in biology and there's some discovery you make that could lead to someone, weaponizing it for an engineered pandemic or something, then you would want constraints on that. So for me right now, open-endedness is interestingly bringing together the threads of the things that I care about.

**Kanjun Qiu:**
I totally resonate with what makes life meaningful. Like if all of the work I do is not useful until I'm dead, what does that say? How do I feel about that? And I read this really interesting quote basically said, "There's only one of you in all the time. You have some unique expression. And if that expression is blocked, then the world will never have it." And so your job is not to evaluate whether your expression is valuable or not, but rather to keep it unblocked and to let it be expressed. I liked that way of thinking about it. With some caveats, like I can't help, but evaluate.

**Joel Lehman:**
Yeah. Thanks for sharing that quote, I really do like that. I got a little bit of a... Like another shiver. Because my job is to be the best me that I can be or something, there's something freeing in that. And like you though, I also, at the same time that I feel that it's an exciting, almost spiritual call to action. If I had been born a psychopath, then my pleasure, it could have been something really terrible. And the world might be better that I don't indulge in whatever my psychopathic whims are. Of course there's some limits to this kind of thinking, but at the same time, maybe broadly speaking with the natural constraints on it, then it makes sense.

**Kanjun Qiu:**
I wanted to go back to something you said earlier about choosing important problems to work on. You've worked with a lot of great researchers in the past. What do you think makes great researchers great?

**Joel Lehman:**
I don't think there is one ideal researcher probably. There are different ways to succeed in research and there's probably lots of different frames to look at that. Qualities that generally seem to be really useful, and it's probably unsurprising, but deep sense of curiosity, some ability to persevere, core competencies. Research is hard and research is about finding things that no one else knows.

**Kanjun Qiu:**
I was just going to ask, are there any specific people where you feel like, wow, this person was really amazing to work with and I feel like I learned a lot from them and they were really great in XYZ ways?

**Joel Lehman:**
The people that come to mind, or maybe the people that I've worked most closely with, the two examples that come to mind are Ken Stanley and Jeff Clune, just because I've worked really closely with them. Both of them have taught me a lot and I respect in different ways. Jeff is sort of like an amazing leader. He's very intelligent and he is creative. Very inspirational at times, knows when other people are hitting maybe that trough of sadness. Use the vision of the ideas that he really thinks will work to get people through that trough. That's a quality that I aspire towards. I'm definitely nowhere near where he is, but it's something that is fun to see.

**Joel Lehman:**
Ken, we've worked so closely for so many years. A lot of the ways that I think are deeply influenced by our conversations and how he thinks. And things I take away from him are kind of like a deliberate approach to research in a sense of having often a contrarian hypothesis. Like one thing you could do in research is try to compete with the herd. It's harder and harder as machine learning gets more crowded. And another thing you can do is to escape from competition by finding your own niche. By exploring hypothesis that you hope no one else would think to explore. It's not easy to do that, but it does, I think have this sort of entrepreneurial mindset. So like an entrepreneur also is someone who is trying to solve a problem often in a different way and has a hypothesis behind why they might succeed in a way that another company won't. And so it's something about taking risks in a measured way,

**Kanjun Qiu:**
Kind of like having a thesis that checks out almost?

**Joel Lehman:**
Sometimes we got a gut hunch, but you might know that there's something interesting that's going to happen if we did this experiment. Not sure exactly what that might mean. You're driven towards exploring that. Ken has a tolerance for that kind of exploration that I think most people wouldn't. You can kind of look at historical examples of other scientists in this vein, or at least they made really big discoveries by playing. I think there's an example of Feynmen spinning a plate or something. And then that led him to some other kind of phenomenon that he was interested in. Or the phenomenon of serendipity more generally in science, which is an underappreciated force. But it's not the kind of thing that grant writing or the narrative of science often encourage. It's often just one person who has this great idea by themselves deliberately or something. It's a little bit of a false picture of what science is like.

**Kanjun Qiu:**
And I think it's a total failure of the scientific system today. One thing we always ask people is, do you have any research ideas you want to donate to the community? Like you feel like I don't have time to do this, but I wish someone else would?

**Joel Lehman:**
I do have this pet attachment to the impressiveness work I talked about earlier. I think there are lots of interesting follow-ups that would be possible with more modern machine learning. So at the time when we made the paper it's with these small neural networks with hand cobbled features. I think that there would be ways to build upon that work in really interesting ways.

**Josh Albrecht:**
One other question, it seemed like you were at least interested in taking a step back, zooming out, looking at the field as a whole. Where does that come from? The motivations behind that? And also now, if you do that and you take a step back, what kind of things do you see in a broader sense?

**Joel Lehman:**
So I think that my interest in things like the retrospectives workshop, which is a project led by Ryan Low I think, about the ML community reflecting on itself. I've become interested in what I see as the shortcomings of the scientific process as it currently is. The shortcomings of even political systems, because there's all these incentives that you can see are just busted that have predictably bad results and seem really intractable to change. That's another problem. But it seems natural somehow to me that your mind tends to drift out to the general.

**Kanjun Qiu:**
Science is an open-ended process. It's basically a larger instantiation of facts.

**Joel Lehman:**
So I think earlier in this podcast, I made what you might call the cardinal sin of a senior researcher, which is talking about the petri dish or about general teaching networks or poet. I failed to mention the first authors. Aditya Rawal is the first author of the Petri Dish paper. Ray Wang is a lead author of both poet papers and Felipe Such is the lead author of Generative Teaching Networks. So I call that the cardinal sin or senior researchers. Because oftentimes in these kinds of venues, it's the senior researcher that's called in to talk about it. And that could be because that person has been around the block, is more well known. Maybe is more comfortable thinking on the higher level about how to present an idea in the context of other ideas, which is kind of natural if you've been around long, but it's not always the case. Sometimes first authors are immensely creative.

**Joel Lehman:**
The reason why I call it the cardinal sin is that there's a way which the incentive system of science seems to elevate the contribution of the senior researcher. Or that of the first author in many contexts and without much grounding in some cases. So it's really interesting how the publishing process doesn't do a good job of distinguishing people's contributions in a really deep way. And also the power imbalances that are involved in the publishing process or the grad student process in general.

**Joel Lehman:**
It could be that, for a particular paper, the first author did all of the work like from the ideation, to the writing, to everything. And the senior author basically did no work, was just stamping their name on it. In other cases it could be there's a more collaborative approach where the senior author might be contributing high-level ideas, helping to iterate in a really hands on way, helping with writing and so on and the strategy. If the author list is the main tool that we have to distinguish that, or the test of time, basically. Where we try to infer from the subsequent papers that a first author writes, or if they later become a professor, you have this noisy signal you're trying to infer like who is actually doing what. It just seems in many cases unfair. No offense meant to my authors. And I apologize for falling into that sinkhole basically.

**Kanjun Qiu:**
I'm really glad you mentioned that. There is definitely a lot of issues with power structures in academia. Do you wish it were better?

**Josh Albrecht:**
I've also started to notice some papers putting in the explicit, these are the contributions of each of the authors. That seems like a good thing for everyone to just do all the time, at least to go to the appendix. Is there any real reason not to do that?

**Joel Lehman:**
Yeah. It seems basically like a good idea to me. I haven't thought through if there are any potential downfalls there. I think the grad student advisor relationship, it just seems at some point that needs to be reformed I imagine. Just because there's so much imbalance of power, not a lot of oversight. And it could be that lot of people, like my experience was that I felt my PhD experience went really well. A lot of people, they can point to their PhD experiences where they felt like they had to do certain things, like give up their weekends or put their advisor on the paper, just because there'll be mad with them if they didn't.

**Joel Lehman:**
The power imbalance can become really, really untenable in some situations. You can imagine if someone is a researcher from another country where not only does their employment depend on this relationship with their advisor working out, but also potentially their stay in the country. It's a very high stakes environment. And you can imagine that that just leads to the potential for abuse. And maybe in many cases it works out fine, but it seems that it would be better if there was some way to moderate that level of power.

**Kanjun Qiu:**
That's a really good point and a good thing to keep in mind for the community. We're almost out of time, so thanks a bunch. This was really great.

**Josh Albrecht:**
Yeah this was great.

**Joel Lehman:**
I really enjoyed it, yeah. Thanks for inviting me on. It's been a lot of fun. Spending some time and I hope to keep in contact with you.

**Kanjun Qiu:**
Thank you for listening to Generally Intelligent. We love feedback and questions, so please feel free to ping us on Twitter at @Kanjun and @JoshAlbrecht. Or email us with any ideas or crushes. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify or your favorite podcast app. Thanks very much. And we'll see you next time.

