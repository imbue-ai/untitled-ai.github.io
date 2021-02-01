---
layout: post
title:  "Generally Intelligent #3: Cinjon Resnick, NYU, on activity and scene understanding"
date:   2021-01-31 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe id="podcast-embed" src="https://anchor.fm/untitled-ai/embed/episodes/Episode-02-Sarah-Jane-Hong--Latent-Space--on-neural-rendering--research-process-eol1vq" width="100%" frameborder="0" scrolling="no"></iframe>

We just interviewed [Cinjon Resnick](), formerly from Google Brain and now doing his PhD at NYU, about his evolution as a researcher, including:
    - How Cinjon started his research by focusing on the intersection of language and games, before running into a wall with this approach
    - How spending time at circuses 🎪 and with gymnasts 🤸🏽‍♂️ re-invigorated his research, and convinced him to focus on video, motion, and activity recognition
    - How this experience led to his paper, “Probing the State of the Art: A Critical Look at Visual Representation Evaluation” and his current focus on “understanding scenes”
    
This time we’re featuring [Sarah Jane Hong](https://twitter.com/latentcodes?lang=en), co-founder of Latent Space, a startup building the first fully AI-rendered 3D engine in order to democratize creativity.

Sarah co-authored [Low Distortion Block-Resampling with Spatially Stochastic Networks](https://arxiv.org/abs/2006.05394) from NeurIPS 2020, a very cool method that lets you realistically resample part of a generated image. For example, maybe you've generated a castle, but you'd like to change the style of a tower - you could then resample that tower until you get something you like.

In this episode, we touch on:

- What it was like taking classes under Geoff Hinton in 2013
- How not to read papers
- The downsides of only storing information in model weights
- Why using natural language prompts to render a scene is much harder than you’d expect
- Why a model’s ability to scale is more important than getting state-of-the-art results

As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!

*Here's the full transcript.*

<!--more-->

**Kanjun (00:00:34):**
Our guest today is Cinjon Resnick. Cinjon was a resident at Google Brain, and he did his undergrad at MIT before starting his PhD at NYU. He's published a wide variety of papers over the years from Generating Music to Language Learning and Game Theory to Self-supervised Learning and Vision.

**Kanjun (00:00:50):**
Cinjon, welcome to the podcast. One thing I'm really curious about actually is the development of your ideas and focus. Right now, your focus is mostly on video and motion, but I know in the past you were really interested in language. Can you explain that evolution a bit?

**Cinjon (00:01:04):**
I wrote this long doc about what I perceived to be the way of roughly how to grow a baby through language. And it starts in my mind with having tasks in front of you, so you have a goal-oriented task, and then the language is the service of that task. So for a lot of babies, parents are telling you, "put the bowl down." And then you start to understand that's a bowl. And then over time, you start to grasp the language and you start to have tasks that are not as primitive, instead they're more built on the previous ones, but you can't really get to that without having the positive feedback loop associated with learning from the task you had at the beginning. That's the larger central theme, is I want to have the world teach a baby through language.

**Kanjun (00:01:48):**
Interesting. What made you decide, "I want to teach a baby through language." As opposed to, "I want to teach a baby through interacting with the visual environment generally with no language?" Why language?

**Cinjon (00:02:00):**
If you look at it from what I'm doing now, maybe you'd be like, "where's the language?" But there was a pretty clear connect the dots in my life, where I really was fascinated with language. Doing this with language made a lot of sense to me because the way I perceive the learning problem there as being, you have a concept, underline it, and then the language is roughly a sign on top of the concept.

**Kanjun (00:02:22):**
That's exactly right. Yeah.

**Cinjon (00:02:25):**
I don't know if it is actually right. If you go read a bunch of like Spelke, it's not clear that is right.

**Kanjun (00:02:29):**
Oh, interesting. So I read a bunch of Spelke. What is it that makes you feel like it's not clear that it's right.

**Cinjon (00:02:36):**
The concepts that she brings up with, you learn like one, two, three, few, many. They appear to me to be like opposite to, or not opposite, but just in conflict with the signposting of what language is, because language would then say, "you need to learn four, five, six, seven, eight," but that's really not what goes on for quite a while, and you can get by for a long time without any of that.

**Josh (00:03:02):**
Decades even.

**Cinjon (00:03:04):**
Yeah. Yeah. Never know what four means. One of my favorite papers is Bengio's means spreading paper. And there it's not even clear that you do need the sign to actually be on the thing to spread the mean. The mean could just be this component that is orthogonal to language. It could be like an embedding, for example, you could spread an embedding around. We could talk about embeddings without having the sign that represents the thing that we think of as being associated with that concept.

**Josh (00:03:36):**
All right, we don't necessarily need a word for it, I think is what you're saying, right?

**Cinjon (00:03:37):**
Yeah.

**Kanjun (00:03:39):**
So this idea of language as like label or sign is not necessarily the, it may be one use case, but we can actually talk about a concept without having a specific label for the concept.

**Cinjon (00:03:48):**
That's right. And that muddles this idea of, as being so straightforward.

**Kanjun (00:03:53):**
Okay. So this must have been at Brain. And then what happened?

**Cinjon (00:04:00):**
I remember just going into NYU and talking with Kyunghyun Cho and he was like, you should come here. We're working on this stuff, we're going to keep working on this stuff. And it just made sense to me, but I would like to devote a long period of time to working on this. I felt, the way I had thought of it then was a marriage of game theory and machine learning, with the goal being to play games on language. So the game is always the task.

**Kanjun (00:04:26):**
What do you mean play game?

**Cinjon (00:04:29):**
So the, imagine the, what we were talking about earlier as the task, we were saying like pick up this bowl, or that could be the game is how do you get the agent to pick up that bowl, so that any tasks can be oriented in a game fashion. The problem with saying any tasks can be orientated in a game fashion you quickly come across, is that we don't have the machinery to really solve games that aren't one versus one [inaudible 00:04:51]. So at least we did it in 2017, things are a bit better now, but we still don't have the mathematical machinery to do that.

**Josh (00:04:59):**
Just like, the sort of reinforcement learning and other techniques we have are just, it's hard to do non trivial games there.

**Cinjon (00:05:07):**
Or that we don't have any of the underlying guarantees that this is going to, like algorithmically converge. And when we're talking about, say, growing a baby, there's, you want to have some sort of guarantees that the thing you're doing is correct. Otherwise you're just twiddling around in evolutionary land. So what we wanted from this is something better than that. When you're talking about something like open AI five or StarCraft works, because it's going to converge, open AI five, you have a complex, but still one verse, one adversarial game, just the teams are different, one verse one. If you were to say, and in Dota, it's a free for all, not five verse five. Now I actually challenge it to actually work. I don't think it's going to work.

**Kanjun (00:05:52):**
Why choose games as a way to express these tasks? Did you consider other ways?

**Cinjon (00:05:56):**
So I didn't really consider other ways. I didn't. I had this sort of like framework in mind and I was really into this idea. I think that's, every good PhD starts that way. It's not that every way that starts that way is a very good PhD. It does start that way, where you have some idea that you're really convinced of, is both going to be important when you're done and like the field will be important, and you're within reach of doing something good. And so I felt this way about games and language.

**Kanjun (00:06:32):**
And then you started your PhD. And so...

**Cinjon (00:06:38):**
Right, right, yeah. As all good ideas, once they actually, hit the medal.

**Josh (00:06:44):**
It seems like you evolved.

**Cinjon (00:06:46):**
It evolved a kind of a, yeah, I spent the first year and a half doing this, like very much doing this. And I don't know if you've seen depth first learning, but there's two curricula that I posted there, which are, one is on AlphaGo and one is on Deep Stack. And they were like, I studied a lot of game theory for that year. And simultaneously I also did some work in this. Like I was doing things on this vehicle paper and which was agents communicating in cars. And then this other concept, this other idea around the capacity compositionality paper and all of the stuff I was doing in that time was towards, what was towards advancing that document that I laid out before, being like, "oh, this is a way towards getting into a positive feedback loop where the world can grow a baby through language and games."

**Cinjon (00:07:34):**
And it just dawned on me over each consecutive time that actually we are nowhere close to doing anything like this. And so this left-field approach is just going to feel terrible working on it because I don't think, while we might do something interesting, I don't think the four or five years time future where this is important, is true, I don't think that world exists.

**Kanjun (00:07:57):**
Interesting.

**Josh (00:07:58):**
Why is that?

**Cinjon (00:07:59):**
When you start working on these things from this approach, you start noticing how little work we've really put on towards this. So back in the nineties, there was a lot of work on roughly this idea. And while some of our machinery is better, the actual advances in what we understand is not much more. Back then, they would ask questions over stuff. If you have two worlds of agents and these agents can communicate through some bit messages and one agent went over to this world, what would happen? Right? And so the things that they had to do that machinery were quite weak, but this doesn't matter, it's just, what would result from that is findings that operated on these two worlds of weak agents.

**Cinjon (00:08:47):**
And now we have findings operates on, we remove most of the world, we just have these two agents now, maybe, and then we have these compositional results that don't really mean much because [inaudible 00:08:57]. It's a disheartening story because it's a very real story. And you, you run into a wall that just suggests this isn't going to work. And then you like take a few pauses and you say, okay, I just, I became disheartened. And if you look at the field, I don't think I was wrong. I think what ended up, what happened was that almost all of that stuff were just spinning wheels for awhile. And then people got a bit less interested and went towards multi agent in general.

**Kanjun (00:09:30):**
What did you decide to go toward after?

**Cinjon (00:09:34):**
This actually coincided with when I started getting really into circus. And so when I looked around at the places that I was training, I was just seeing everyone using the camera all the time to record themselves, to film and say like, what's going on with my technique, what's going on with all these things. And it just seemed really obvious to me that there was a thing here that could help them, that I could probably do, which was roughly activity recognition for motion.

**Cinjon (00:10:04):**
That as not a problem that ever interested me. And to be frank, like at the outset of looking at that problem, I would have said, this is the wrong environment to do that as well, because the right environment to do a problem like that, is a place with lots of resources and scale. But after I started looking into it, I would see other things that are more suited for this environment. And also just parts of the problem that I came to really love.

**Kanjun (00:10:30):**
Interesting.

**Josh (00:10:32):**
Is that where the Probing the State-of-the-Art paper came from? Is from like the circus angle, the like doing activity recognition?

**Cinjon (00:10:39):**
Yeah, yeah, yeah. That was it. That was the original genesis of all that was like, we, I was doing that. I was gathering lots of circus videos. And then I started working with the, these different gymnasiums across the country because they had a similar problem. And so they put their cameras in there and then I was working with some well, like I was very closely working with a couple of guys and they, one of them was a judge and also had judge friends. And so they would annotate all of it. And it's a great dataset that no one gives a shit about, but it's like a really good data set for activity recognition. Because if you look at, no this, I think of this as being a really core problem, in particular for things like, if you want embodied intelligence, you need to be able to recognize what people are doing. But the issue with that field is almost all of it is coarse-grained.

**Kanjun (00:11:33):**
What do you mean coarse-grained?

**Cinjon (00:11:35):**
So like at a high level, it doesn't matter if I'm asking you, is this swimming versus tennis because you just need one image, right? So you just need one image to decode those two, to figure out those things. So what people try and do, is they try and add more things that are like pool related. So now you'll have, is this swimming, is this diving, but you rarely, if ever get, I don't think any data set has this except maybe dive in 51, have, is this breaststroke versus pre-style versus that kind of stuff.

**Kanjun (00:12:08):**
Very fine grained.

**Cinjon (00:12:10):**
Fine grained. Yeah, that's a different story because, so for gymnastics, for example, each of these actions happen on the course of one to three seconds. There's a five, I'm forgetting that number, I think let's say it's 500 in the men's credit points. You have to recognize them from a really sharp perspective, like there's little differences and those little differences, most of these models can't actually address, towards actually solving activity recognition. And none of the models we have today will work. But if you ever talk to a judge or like someone who's been in gymnastics for more than five months, if you spent like a few months in something, then it's not just so you can recognize the stuff you've already seen. You actually do a great job of recognizing new stuff. And so now I'm going to bring this back to language. I think that there's something like a grammar that happens in your head. This is a hypothesis. I don't know. But I think that what's happening is that you're developing a grammar for human movement.

**Kanjun (00:13:12):**
So it's, as you become more expert in the activity...

**Cinjon (00:13:16):**
Everything, in everything. Yeah.

**Kanjun (00:13:17):**
Any activity, you're building some kind of grammar.

**Cinjon (00:13:19):**
Yeah.

**Josh (00:13:24):**
Yeah. I think that was a really interesting idea. And I think that probably applies beyond, like motion is one example, but it's also, people who taste wines or like pretty much anything you pay attention to, you end up developing this like big set of concepts. Like for me, wine is like, better wine. For some people, they have a lot more nuance to it, for me gymnastics, guess it's male or female and they're moving. Like I don't know, like they're spinning or something, but if I had watched it for five months, I'd probably know a lot more. Yeah. Yeah. I think that's an interesting way of describing it.

**Kanjun (00:13:53):**
When you say grammar, what exactly do you mean?

**Cinjon (00:13:57):**
So if we stick with gymnastics setting then we're talking about is, okay, men's, women. So we'll take the binary thing first. We're immense. Okay. So now what event is this? There's five events. So let's just say rings. Now we're in rings. When you do a movement in rings, there's a bunch of things that happens with your body, right? The rings do a little bit, but most of the time it's, your body that's doing different movements. And I think the grammar of your movement is what's happening here. And so for example, I, in circus, I do this thing called straps, and it's been really heartening to me to realize that over the last few days of training, that nine months didn't actually do too much.

**Cinjon (00:14:42):**
Yes some stuff is a little bit harder, but my body still remembers everything. And if I was to try and learn something new right now, I have no question that I would be able to quickly do it. Or if I see someone doing something new, because I know what the motion of the body should be. Can I describe it to you? I can also describe it to you. There's, that doesn't happen in the first few months. It happens a little bit later I think. But I can also tell you, this is what your limbs should do. This is where you should feel it. So I think there's roughly a grammar for each thing, each body movement, that accompanies motion. And this is, this could be thought of as the label that we were talking about earlier. I don't need to know this to describe it to you. But if I had this, I could tell you, this is what it is.

**Kanjun (00:15:31):**
And communicate it to me? Right. You're developing conceptual. Yeah. That's interesting. It actually reminds me of one hypothesis I have about learning, is that, here's an example, if you are trying to learn algebra and you don't know any numbers, it takes a very long time to learn algebra. You have to first learn what numbers are and hold all your numbers in your working memory while you're trying to understand algebra. So in, in some sense, like if you haven't learned numbers yet, you're like missing some slightly higher level representation that is necessary for you to learn the next concept. And there's some kind of building block thing going on here where like you, you have to be in some like adjacent possible, of building blocks that you've already internalized in order to learn this new thing.

**Kanjun (00:16:15):**
And it feels really related to your activity learning thing in, in circus, where if you have learned all of these moves, your body knows all these moves. Now you can somehow, you can learn new moves there, like some construction of the old moves, but I can't learn the new move because I don't know the old moves, like my, it's not in the adjacent possible. It's too far.

**Cinjon (00:16:36):**
I think you said it really well. And I agree very much with that. That thesis was also what went into depth first learning, which is that, if you are growing, you can't put a leaf onto a tree that doesn't exist. So if you want to actually understand a paper, you have to have first grown the acorn tree that represents this paper. That is underlying issue.

**Kanjun (00:16:54):**
What is depth first?

**Cinjon (00:16:55):**
depthfirstlearning.com.

**Kanjun (00:16:56):**
That's really interesting, with your new focus, how do you think about the hamming question? Like what is the most important problem in your field and are you working on it?

**Cinjon (00:17:04):**
I feel like I'm actually doing the right thing here. As in, I feel like I am addressing an important problem and I am working on it. So I want to couch it from the, because I, I feel like that's too strong and I think that there's a reason where you act too quickly why that's too strong. I'm gonna say that I think one of the most important problems in ML is this question about distribution generalization, arguably this is the central most important problem, but there's a lot of other problems that people work on and they call it different things. But it's probably really just under distribution generalization. If you want to do something different, and I usually hate doing this, but say like most of the common problems in AI are the ones that I think are dealing with learning in the actual world. So embodied learning rather than other components.

**Cinjon (00:17:49):**
So I'm going to, I'm going to say then that what I perceive that I'm doing right now, which we haven't actually talked about, is understanding scenes, and I think that this is a driving force in both these directions. In order to get to robotics and body intelligence or all of the things around quickly, get, generalizing television. I think you really do have to have some sense of what is happening in the scene. And this can come from video, which is in how I've been thinking about it. But lately I've been thinking about it much more in a static sense. And how do you get the static version, which is just definitely under defined, but...

**Kanjun (00:18:26):**
What do you mean by, in a static sense?

**Cinjon (00:18:28):**
Oh just like a single RGB image or a single RGBD, that's what I mean, I just mean not multiple video version, not multi [transing 00:18:36] So the important problem that I'm pointing out here, is understanding scenes. And that, I think is actually, there's another question you have on there is really underrepresented today. So I'm going to point out a paper that I think is not really getting enough attention. It's actually two papers, but the second one is one is MetaSIM and MetaSIM II. Almost no one seems to know about these two papers, but they're good. They're really good. The idea here is, we're going to take a whole bunch of RGB images, and we're going to assume that these are from a distribution of scenes. And now we want to have a 3D renderer, render things that are, have a similar distribution to the scene.

**Cinjon (00:19:21):**
So the original RGBs could be real, could be SIM, they're actually usually real. I think all the stuff in the paper use KITTI, and the render obviously is going to render things that are SIM because I mean, that's what it does. So it has a library of assets that it gets to use in order to generate a similar distribution of scenes. You need to have a prior on what are the possible things you could put in the scene, but I don't actually think that's going to be a problem downstream, because I think that if you like include a bowl in your prior, but there's no bowls ever in the scene, I don't think it's going to end up using it.[inaudible 00:20:01]

**Cinjon (00:20:03):**
Now, note what I'm not saying though, is I'm not saying learn a single scene. You can't do that. So you can't take, whatever the scene behind me with the curtains and like the brick wall, you can't, it's not going to do that. It's not going to reproduce that scene, which I think is really important, but it's not something I was trying to do, what I was going to say is that there's a distribution over the scenes you care about. And we want to learn that.

**Kanjun (00:20:28):**
I see. And so what it can, what it does, is basically learns distribution based on whatever scenes you're training on. And then it can generate new scenes with the same distribution. So like bedrooms.

**Cinjon (00:20:41):**
Exactly. Right, exactly. So on the paper, they do this on self-driving car scenes. So you have things like cars, roads, trees, street signs, houses, that kind of stuff. They use kitty, and it does pretty well actually, like surprisingly well, with an unsupervised version, right? There's no supervision here, except for the fact that you give it the prior over what objects could be somewhere in here. And you give it obviously, the data.

**Kanjun (00:21:10):**
Okay. Interesting. There are plenty of generative models that generate from a distribution out there. What is it that feels significant about it to you?

**Cinjon (00:21:18):**
So I, I view the line of work that says, we have a scene and we want to reproduce the scene with 3D render, as being especially important for the embodied stuff down the road. There's some accumulation of papers that suggest you can do domain annotation. You can do random organization, all of those things work. But the best thing is if you can put the robot into actual houses, right? If you can put the robot into the houses and start doing stuff, that's great. What if we though had, took all of YouTube, all of the houses there, and we just took those scenes and we put our robots in those scenes because we have the renderings, we have the 3D engines that can do that.

**Cinjon (00:22:03):**
So the 3D engines are good enough now. And the simulations are good enough. The thing that we're missing is understanding of what's actually in the scene. And what you get by doing this in the 3D render is really interesting because if you can say, all right, what's the bowl. Then we can program in the affordances of a bowl. So now you can skip the step where the robot has to learn the affordances of the bowl, but it still gets to operate and figure out what actions to do.

**Kanjun (00:22:32):**
I'm a bit confused. How do you learn the affordances of the bowl? Oh, I suppose...

**Cinjon (00:22:37):**
You don't. The renderer knows the affordances of the bowl because we've told it. So like bowl, cup, the fact that liquid can go in here. Now the robot just has to learn how to pick this up, that it can drink from it, that you can put liquid in it. But the fact that you can put liquid in it, we already have taken care of by the vendor, by the engine. And I think this is, so right now, like the grand challenge, according to a bunch of people like Sergei Levine, et cetera, is to do rearrangement as a task for embodied intelligence.

**Kanjun (00:23:14):**
I see. So rearrangement in embodied intelligence is basically, you have a scene and now you want some object in the scene to be somewhere else in the scene. And so you want the renderer to be able to move that object to the other place without messing everything else up.

**Cinjon (00:23:26):**
Totally. It can be more complex than a single object movement. Of course. Yeah.

**Kanjun (00:23:29):**
Got it. Got it. And does everything in the scene, like in the new scene already have to be in the old scene, can you add new stuff in the new scene?

**Cinjon (00:23:39):**
I don't remember if they do that in their challenge, but I would say yes. And I've been thinking about it as if yes. So the way I think about it is that there's a can on the table and the output should be the can is open. Where is the can opener? It's in the drawer because that's where can openers are and you have to understand that. All of this works, if you can grasp what is the scene graph, in advance. Okay. Sorry, I didn't say this earlier. So when I think of scene understanding and that distribution thing I was saying earlier, that distribution is a distribution of scene graphs. So if you imagine a road scene, the way the scene graphs work is that you usually have a left and a right. Sometimes you'll have more lanes, but then the things that are on the lanes are child, are children of the lanes.

**Kanjun (00:24:27):**
I see. And the lanes are not attached to each other at all?

**Cinjon (00:24:31):**
They're usually attached to a root or something else, but like usually a root.

**Kanjun (00:24:36):**
Got it, got it. So a scene graph is meant to represent what objects are like on other objects in the scene.

**Cinjon (00:24:45):**
Okay. You get to define this. We can say that this is the definition we've made, but you can define it if you want.

**Kanjun (00:24:49):**
I see.

**Cinjon (00:24:51):**
The thing though, is that all of the generative approaches here I'm talking about, are not, they're not generating the image from pixels, they're generating the scene graph and then letting the render use that scene graph.

**Kanjun (00:25:07):**
I see. So the sim is a learning a distribution of the scene graph.

**Cinjon (00:25:13):**
Yeah.

**Kanjun (00:25:14):**
Not of pixels.

**Cinjon (00:25:15):**
That's right. Sorry, I was not clear about that.

**Josh (00:25:19):**
Do you feel worried about the like explicit nature of the scene graph? Like with the example of the wall in the mirror, like if we move the mirror down, like just this much, and then we actually put it on the dresser and tilt it back, so it's actually resting on the dresser but also on the wall. Is it really, has this sharp transition from what, it was on the wall, but now it's on the dresser or now it's on both of them. It has this like weird, like explicit, discreet kind of nature?

**Cinjon (00:25:42):**
Totally. And I think that's a great question because that gets at what is, we're getting closer and closer to the stuff I'm working on by the way. But that gets at what is semantically possible and what is in this distribution. So there is a bunch of work by my advisor recently, like half of it in chemistry and half of it in language, where he's asking a similar question and the question there, it looks like you have this chemistry graph. What is possible in this concept? Like we could change one of the elements out into two different atom and it's still okay. And so the way they try to address it, there's, they use an auto coder. And then for your example, I think what would happen is, sometimes in the data or enough times hopefully, the de-noising system or whatever it is that we have over this would be able to see that mirrors can be on desks or that this operation of this object can be on top of another object, it's okay. And so there'll be, there's some room for maneuvering here.

**Josh (00:26:40):**
Because you're learning a distribution. It's not as bad because it's not like when we see this one thing ever once and you get to see like a whole bunch of different things. It's like this sometimes, it's like this some other time. So it's more probabilistic thinking about the graphs instead of so explicit.

**Cinjon (00:26:53):**
That's right. That's right. That's exactly right.

**Kanjun (00:26:56):**
Interesting.

**Josh (00:26:57):**
And so you said we are getting closer and closer to your research, so the final step.

**Cinjon (00:27:02):**
The thing that I've been thinking about, is what is permissible and what is not in a scene graphs, that you already have a distribution. So as an example, assume the self-driven car earlier, what happens if you imagine a car being completely turned around, so it's not heading towards you. And the thing is that like, it happens sometimes and very rarely, but sometimes cars go the wrong way on, on roads. And this is just the same. We should understand this scene just the same, but it's not the case that we have expectations that models will actually work in this way. And so what are the things that are unlikely to come up in this, in the example with say, you know, it's not like to be caught in that way as a permissible thing, but still are okay.

**Josh (00:27:58):**
Yeah. It's about making this thing more robust to those sorts of things. We need to understand this about the world, but it's not going to show up if you just sample a bunch of normal data

**Cinjon (00:28:07):**
Exactly.

**Josh (00:28:08):**
Yeah.

**Cinjon (00:28:09):**
As I understand, every car system, for example, is built to be reactive to these kinds of things. And the thing that I'm thinking about is, how can you be proactive? How can you figure that out? So that's one branch, another branch is, how can you over-fit to a scene? So let's say the mirror thing earlier.

**Kanjun (00:28:36):**
You want to over-fit to the scene.

**Cinjon (00:28:37):**
You want to over-fit to the scene you want, you want to get it perfectly, you want to get the perfect scene.

**Josh (00:28:40):**
Let's go in to the proactive one first, just since we're already on that line of reasoning. But the other ones also really interesting. Let's come back to that one. So yeah. How do you actually be proactive about learning this instead of reactive?

**Cinjon (00:28:53):**
The approach that we've been taking is, what you're trying to do is search over this world and see you have an underlined module. You expect this module to fail in some specifically real way. So now you want something that can search over the space of possible things that will fail it, while still being in the confines of what is, like human would say, this is okay.

**Josh (00:29:18):**
So it's like a constrained adversarial problem. Like you're not allowed to do the same things, but you want to find it?

**Cinjon (00:29:25):**
Yeah. But in particular, note this is quite different than the usual adversarial setup, because we're not talking about pixel shifting, we're talking about actual semantic shifting, and that's what you get when you like, you've got this because you have the render and an actual construct, like the construct being, sort of the same graph.

**Josh (00:29:46):**
Going back to just one more question on the scene graphs and the search over the scene graphs. How, how do you know what transforms and what parts of the space are allowable, versus not like car, okay, we know cars are objects, are objects to you, like at higher transformations are probably fine for objects. So how do you know which of these transformations are reasonable? Can you put a car on top of the building? There's all sorts of things that are like, yeah.

**Cinjon (00:30:12):**
I don't have the straightforward answer, this is correct. But I'll tell you my hypothesis. And I'm telling you that this is what I'm directly working on, but the hypothesis I have is that you can treat this like a game. So if you have one agent who's trying to, trying to basically not do that, trying to get things to fail, and another agent that's trying to fix things, then they think the tension between the two will lead them to ride the Ridge, so to speak, of what is semantically correct or not. And the reason why I think that is because I think that the second agent is going to put things in a place which the underlying perception module is going to understand. And the only things that really understands are the stuff that is real. This might just be bullshit, it might just find, might find weird pockets that it succeeds in, where cars are on top of buildings.

**Josh (00:31:08):**
That kind of reminds me of a paper that I saw. I think it might've read it from Nerves this year. That was very much about this, but in a more simplified setting, but maybe it's useful where it's a maze task. And it was this adversarial game setup, where like you're trying to learn navigation, and like 2D maze, a really simple agent. And so it would start with a really simple world. Okay, you just have to move to the right. And now you found a thing like, hooray, good job. But then they're like, okay. So how do we like give a sort of curriculum, level up more and more difficult levels? And they first tried this like game approach where they have like, okay, we'll have someone else create the mazes. But it made mazes that were impossible. Where like put food on it. Just like inside of things you could never get to, this is not helpful. And so instead what they found is that, if I remember correctly, they optimized for, it's not pure maximization for the adversarial thing.

**Josh (00:31:56):**
They need to like maximize the minimum or something like that, or minimize or something like that. But anyway, some sort of like distribution of possible things, like sometimes we'll make them fail, but it never made everything fail. And so optimizing this in a slightly different way, they were able to get you where you were. [crosstalk 00:32:10]

**Cinjon (00:32:10):**
Can you send this thing?

**Josh (00:32:11):**
Yeah. Yeah. I'll say I'll make a note and I'll send it you afterwards.

**Kanjun (00:32:15):**
Another thing that you talked about earlier was, how can you over-fit to a scene, like regenerate a scene, precisely. Why do you want to over-fit to a scene?

**Cinjon (00:32:27):**
So the motivation for that comes back again to something like, actually this was a popular paper that you guys might remember, ‪[Xue Bin Peng](https://scholar.google.ca/citations?user=FwxfQosAAAAJ&hl=en)‬ has a really good work. And he had this paper a few years ago where they had a robot that could do back flips. It was like a simulator robot. They put a jet pack, they did all kinds of stuff. And this thing could do all these cool motions and the way it learned that was just from video. So, so the way this worked is, they would get those key points from these videos they found of people doing back flips, and then they would just have the model optimize for being able to match the key points of it, to the key points of the human.

**Cinjon (00:33:09):**
So there's one thing that I want to point out about that though, which is all of the examples they have there. They rely on having a single, a single force against the agent. And what I mean by that is, the only thing that exists in this world is the normal of the ground. Do you want to do something on a pommel horse on rings? If you want to manipulate, interact with the world in some way, in order to generate your cool trick, you can't do that because you don't have an understanding of where you are in the scene. There's nothing that says this cup over here, can we pick it up? There's nothing that says those are hanging a ring or something you can hang from.

**Kanjun (00:33:54):**
Because you don't understand like your position relative to the ground and that there is gravity and all of these other things.

**Josh (00:34:00):**
So the gravity is a universal one that one's everywhere. I think that's what St. John is saying, is that the reason that Jetpack one works is that gravity just everywhere. It doesn't matter. You're always doing this thing, but you're only doing this thing relative to gravity. You can't, you can't do a ring trick if you're two centimeter just to the left of the rings, you reach up and say, "oh, no, you're missed."

**Cinjon (00:34:17):**
Yeah, exactly. So if you just don't have an idea of where the things are in the scene, like the ground, you never, don't care. It's like always there, it's always doing the ground thing, whereas like objects, you need to know where they are and what they are and what they allow you to do. So when I like walked into a, when I have my robot walk into a gymnasium, it needs to understand the scene in order to be able to do anything at all.

**Josh (00:34:48):**
Except back flips.

**Cinjon (00:34:49):**
Except back flips, right.

**Kanjun (00:34:55):**
I see. And so you want to over-fit to a scene so that you can precisely understand everything, every object in the scene.

**Cinjon (00:35:02):**
Yeah. It's all about just getting that, what are the objects and where they are. Just basically the scene graph.

**Josh (00:35:07):**
So is this sort of like a scene graph version of Nerf or something like that almost.

**Cinjon (00:35:13):**
So there is actually a scene graph version. I don't know if you've seen that version, You've seen this? They have a Nerf that's a compositional Nerf. Who did this? Yeah, Michelle Guo made Nerf, compositional.

**Josh (00:35:24):**
I think I met less in the rendering sense and more in the, like trying to make a representation of a scene, like Nerf is sort of over-fit to a particular scene. It's like the network is learning something about a situation.

**Cinjon (00:35:34):**
Maybe.

**Josh (00:35:35):**
Saying something different, Would your over-fit to a scene example?

**Cinjon (00:35:40):**
I don't know if it is, so what's interesting about that concept is that Nerf is like, Nerf is building this up each time, right? If you change the, you changed the theta to over here, the Nerf regenerates the whole thing, and it's all built into the network. But what I'm stressing is that I want to go into rendered world land and to do that, I need at some point to have a full sense of all the objects. And so, as an example, if I could, I mentioned earlier, if I could take all of the YouTube scenes and get the distribution, like more in particular, if I can just get the exact for each user, but I don't care how much computational resources and that cost. If it takes me like an hour to get every scene, I'll still get 24 scenes in a day. And that's amazing for robotics.

**Cinjon (00:36:24):**
It doesn't much matter to me whether the computational takes time. The important part is that there is an object representation I can put into a render, really trying to make user.

**Josh (00:36:36):**
So you want to go from either a static image or a video to the scene graph basically. Like you want to convert from like raw image or raw video to scene graph.

**Cinjon (00:36:47):**
Yeah. I guess I think if I was to sum up what I, what we just talked about with respect to the things that I've been focusing on is, I was looking at a grammar motion or perceiving it that way. And now it appears that I'm looking at a memory of a scene.

**Josh (00:37:05):**
Obviously those two things are probably pretty related, right? Like, maybe you're sorting, my sort of guess is that you're sorting the scenes because it's hard to do the motion until you have the scenes. Like the motion just seems more complicated. It's plus scene, plus extra information with time.

**Cinjon (00:37:20):**
I think that's true. But I actually want to push that back on you a little bit. Do you feel like that's important for the baby question?

**Kanjun (00:37:27):**
Grammar of scenes.

**Cinjon (00:37:29):**
I feel like they're really different for the baby question that they seem in my mind to be, I don't know how important the grammar in motion is, except for maybe humans to a baby. It's not clear to me. I feel like doing the breakdown of the scene seems really important, but I don't know. I don't know.

**Josh (00:37:47):**
Yeah. I think actually it's probably not that relevant for like your first six months and there's a human moving around, doing something. You will most certainly need to understand that for the later stuff to figure out, okay, why are they like opening the cupboard or making food or there's all sorts of, it's just really hard to understand humans if you don't understand motion. And like motion of humans and motion of other objects and the cat or a dog, or the way those things move into form. And a lot of that emotion tells you about, is this thing an agent or not, that all said, I think you're still mostly right. Especially for early baby learning.

**Josh (00:38:17):**
I don't think the like grammar of motion of animate objects is like the most important first thing. It's probably much more important to get the scenes. Maybe the only place the question really comes into it is, ego motion more than anything else, motion more about like, "hey, I moved around. I'm like, I understand how I am relative to these other things. So now I understand the scene better." And that has like a way of, or like a mechanism for scenes.

**Cinjon (00:38:41):**
Having that 3D model in your head of what you are relative to [crosstalk 00:38:45].

**Josh (00:38:47):**
Actually one, one interesting thing about babies. There's this, basically like they don't do very well on a task, which is like, you have a pyramid and you have to rotate like this. And there's like, go back to the pyramid, with babies up to a certain age, or like, that checks out. Babies after a certain point are like, wait, that's weird. And you can tell by like how much attention they think, but the particular time when they transitioned from, that checks out to like that's weird, is when they're able to like grip things, manipulate them and move them. And so the fact that those two things are so tightly correlated, it really points out that, Oh, it's actually probably really helpful to have those extra signal.

**Cinjon (00:39:22):**
Yeah.

**Kanjun (00:39:26):**
Interesting. One thing I did want to ask you about was, I really, I found the [Ridge Rider](https://arxiv.org/pdf/2011.06505) paper really interesting, and I didn't have time to go through all of the math and the code and understand how it worked exactly.

**Cinjon (00:39:45):**
I was going to say that you were the one that I see.

**Kanjun (00:39:51):**
I felt like it is the kind of work that people listening might be interested in. And so I was wondering if you could do like a one sentence, actually I can do a one sentence explanation of what it is, and then maybe, maybe you tell me why I'm wrong.

**Cinjon (00:40:07):**
Yeah we can do that.

**Kanjun (00:40:07):**
So it seems like basically most of the time we use stochastic gradient descent in order to find a good solution, but there are actually many good solutions that are minima and those different solutions have very different properties. So some solutions may have shaped bias and other solutions have texture bias. Maybe you want to be able to choose between the solutions and access the one that you prefer. So it sounds like Ridge Runner follows the IA vectors of the hessian in order to find all of the solutions. And then you can pick the one that you want. You can locate all the solutions on the surface, and then you can see what they all look like.

**Cinjon (00:40:45):**
Yeah. That was great. There's one small change that makes that, which is just is not going to find all solutions necessarily. But yeah, it's going to try and find many solutions and you get to select from them. That's right.

**Cinjon (00:41:00):**
Yeah. A bunch of people have asked that question. The thing is that it's not doing the full hessian. So it's not like it's that slow, but it's still, it's not like we got it to work on a big dataset. We even tried, to be frank. This was, let's just get something showing. However, I will point out that towards practicality, the colored amness stuff, that wasn't easy to get that score. So we, we did, we did do a lot of playing with it, to try and get at that. Everything else in the paper actually was like, worked pretty okay. I would say that how practical it is, it's kinda like all first things that come out where you say, what the is that? If you go a little bit further past, if you got fewer papers down. If people keep working on this, then I think what you'll get is actually more optimized stuff.

**Kanjun (00:42:00):**
I was wondering actually, how did you get to this solution? Because I thought it was really good.

**Cinjon (00:42:04):**
To this idea?

**Kanjun (00:42:05):**
Yeah, this idea.

*Cinjon (00:42:06):*
Yeah so this was, this came from, this was largely Jacob's idea. Like almost from the beginning, right? Actually definitely from the beginning, but I'm trying to pull myself back. So I remember in the beginning he was like, I need help with this idea. I feel like this has legs. Here's what I'm seeing when I do this on the symmetry problem, the one with the agents playing the game. And what was interesting there was how the eigenvalues, they categorically look as they do, as in there are certain class. I don't remember the, the terminology we use, but there are classes in the, in the eigenvalues, but you could say, those are the same solution and these are the same solution [inaudible 00:42:57].

**Cinjon (00:42:58):**
And so once you start noticing that, there's something that shouldn't happen to here, where if you just, if you follow any of these in the same class, you're going to have the same solution. So, that's done. And so now you have, you can go from there and you end up, when you do this, you find that it does, the graphs are figure six. You find that it actually does get to categorically similar solutions for a bunch of them. And then three of them look different. One of them being the highest average path. So that was like the beginning of the way where it was in the toy game, where we definitely know what is the right solution. The hessian just fall into action like this, we'll find subsets that are the same as well as the likely best one or the best one. And then all of the things after that are, we were working, we did this stuff on the, the OOD separate code amness, because that's, that was like the benchmark at the time. Does that answer your question? I'm sorry, I didn't directly actually answer your question. Like, how did this came to be?

**Kanjun (00:44:08):**
Yeah.

**Cinjon (00:44:09):**
This came to be from that observation.

**Kanjun (00:44:11):**
Interesting. That's really interesting observation.

**Cinjon (00:44:14):**
Here's what I'm going to step out and say one of the problems with this paper, or like one of the problems with idea, is that, let's imagine you had some feta and you're not at a minimum, because you know, you can keep going down. Let's just say that. That's what it looks like. But you could also keep riding the Ridge. You don't know, you don't really know because you don't know that if you go down, that's going to be any better than if you keep going. And like the wider point to them, I guess I'm making, is that at, at any point, you don't know if this is the right one to go down and you can't do all of them.

**Josh (00:44:54):**
Yeah. So how do you like optimize for diversity here almost, is what you want, right?

**Cinjon (00:44:59):**
You're trying to optimize for diversity. So, you know, I guess I'm a little bit skeptical that this is going to be any better than, it's definitely better than what you do for finding diverse solutions, because as you're gonna run at once, but I'm skeptical, that's going to add, it's a better approach than say, some of the other things that are exploring like legitimate. How do you find like texture, but the implied things? Or any of the stuff that is, is more geared towards saving the other parts of discussion you're having around human implied learning? Because definitely there's a lot of human implied learning, which is associated with shape, but, but that is like a real motivation here, which is, we don't want to just find the texture solution. You want to find both because one of them is useful in some cases, some is useful in another, and yet there's no guarantee this is going to even come close to doing that, because you don't know, you just don't know.

**Kanjun (00:45:46):**
I see.

**Josh (00:45:46):**
There might be a distribution over that, those shape and texture ones, where in this particular network architecture, it's like much more likely to find in texture than shape. So you could use this technique to find it, but it just might be really expensive.

**Cinjon (00:45:59):**
That's a great example because, or even like to make it very clear, maybe your data is always sending you towards texture, for what, for some proclivity of the data.

**Kanjun (00:46:11):**
That makes sense.

**Josh (00:46:12):**
Yeah. There was another related question, which is, looking at your papers on Google scholar. There's a lot of diversity, I would say, and many different interests. What I think is really cool. Like how, are there any other, besides the ones we talked about already, are there any other like broad themes that connect all of those? Or how do you think about, about all of that?

**Cinjon (00:46:38):**
My brain time and then it was the first half of my PhD was this machine. Then the machine learning and language and the second half has been around computer vision. That's kind of how I see it. And I'm trying right now actually, to make the PhD coherent with this, these, the stuff I've been talking to you about, searching over scene graphs. If you look at, if you look at search and vision, there's been almost nothing that's really done. And I think that's really missed because the, one of the most important problems going forward I believe, is inverse graphics and searching over inverse graphics is what is very possibly what's going on in your brain.

**Cinjon (00:47:15):**
When you think of a purple flying monkey, it's like there was something there that triggered. We both know that, we all thought of a purple flying monkey, but how did we get there so fast? What, I'm pretty sure we search. I feel like we searched over some words.

**Kanjun (00:47:32):**
What are we traversing to get to that? 

**Cinjon (00:47:32):**
Yeah, yeah, no, I don't know the answer to that there, like in the brain wise, but I feel like in models, that's what we should be doing as well, is some sort of search over inverse graphics. And so I'm trying to marry that a little bit, but the real answer is just that I feel like I want this to be coherent and otherwise this feels empty to me.

**Kanjun (00:47:51):**
Moving toward the end. Are there any ideas that you don't have time to do, but you would love someone else to do or you want to donate to the community?

**Cinjon (00:47:59):**
Oh, there is an idea that I want other people to do. So there's actually two things that come to mind, let me try and find it. Okay. So here's one which is actually like fairly boring, but I think important, that almost every way that people are trying to evaluate scenes these days, is by an evaluation metric that relies on a perception module, a detection module. So they train them, they get their scenes, they render their scenes. Then they ask, does this improve detection on a held out evaluation task of real data? And I, I just, this is bad. This is bad. And people are doing it because this is the easiest thing to do. The thing that I've tried posing to a few people now, is to replace that with a rearrangement. So you have a scene graph understanding where the model is given the scene graph as input instead of at every step instead of the RGB. But like your scene graph, needs to be good in order for it to be, the robot you're able to do here.

**Kanjun (00:49:04):**
Actually, I have a specific question, which is, you said people try to evaluate teams via a detection module. And so is what you're saying that they try to evaluate scenes is the detection model, does it classify objects in the scene? Was like that what you mean?

**Cinjon (00:49:19):**
Yeah, it does detection. So it does. Here's the object and its boundary box. So then your performance is the average precision of this.

**Kanjun (00:49:28):**
Got it. And you want to evaluate scenes instead, based on how well can the model handle rearrangement of objects in the scene?

**Cinjon (00:49:38):**
Yeah. So we're talking about evaluating models that do scene graph understanding. So they're generating scene graphs of this scene, of the one that the robot is in. What they're getting at is they produce a lot of data of these scenes. And then the detection module is trained on this data and then asked, how does it do on real data? So it's essentially a task. So this is the common evaluation metric, and then there's just problems with it. So as an example, does improvements in scene graphs understanding actually lead to improvements in this task and not clear that it would. You might just end up with fewer objects because if you have a bad scene graph thing, but it just puts stuff everywhere, then you have to detect more things. Whereas if you have a robot walking around, it really better know what the scene graph is. If there's no, there's no cup in the place, or if there's too many things, it's just going to fail.

**Josh (00:50:41):**
So you're saying rather than doing taction, you want to evaluate on whether it gets the structure of the scene graph, correct?

**Cinjon (00:50:51):**
Yeah, yeah, yeah. The thing that you're trying to do.

**Josh (00:50:53):**
[crosstalk 00:50:53] Not just some detection per scene, bounding box or something, but literally is the structure of the scene and the structure.

**Cinjon (00:50:59):**
That's right.

**Josh (00:51:00):**
Because that's what was in your model.

**Kanjun (00:51:02):**
If people are evaluating models that do scene graph understanding, using a detection model were they see if they properly classify objects and draw bounding boxes around them. And what you want instead is for them to evaluate whether the scene graph was properly constructed. And you do that by using the rearrangement task.

**Cinjon (00:51:23):**
Yes. It doesn't have to be perfect and you could still solve the rearrangement task, but it can't be that off. Like if you make a scene that has, where the desk should be mostly empty and you put all kinds of stuff on it, that'll help detection because then detection has to learn how to finally separate things, et cetera. But it does badly for rearrangement.

**Kanjun (00:51:48):**
Because?

**Cinjon (00:51:48):**
A, it's a way harder task. So you're immediately, your optimization is a shit situation, but B, like, that's not what the desks usually look like. And so if you just put lots of keyboards all over, that's just not going to help.

**Kanjun (00:52:08):**
Yeah.

**Josh (00:52:09):**
But it will help you to detect keyboards.

**Cinjon (00:52:11):**
It will help you detect keyboards very well, yeah.

**Josh (00:52:12):**
Do a great job on that.

**Cinjon (00:52:15):**
Yeah. And so you would standardize the robot that's used, then choose, all that. And it's like, all of that is already given to you in the rearrangement benchmark paper. And so you really just need to, we just need to change this eval because it's complete, definitely evaluating the wrong thing.

**Josh (00:52:33):**
Cool.

**Kanjun (00:52:34):**
Interesting. What's the second idea you wanted to donate?

**Cinjon (00:52:37):**
Oh, okay. This is a little bit tougher conceptually, but I think we can pull it off. Let's imagine that I was to hold this cup up. And so this is our scene right here, it's a person and then a cup as a child. And then what I'm going to do is, I'm just gonna put this cup down. Okay. So now I don't have it, he's is not a part of me. He's just his own node. So what I, what I'm going to say there is, we've made an edit to the scene graph where this was a node. I mean, the node would basically stay the same, it's still this cup. But instead of it being this position, that's relative to me, it's now this position, which you can't see, but is relative to the, the desk.

**Kanjun (00:53:24):**
Just to confirm the edit that you've made is the cup went from being a child of you, to being a child of the desk?

**Cinjon (00:53:31):**
Yeah, exactly. Okay. So I'm going to use that example to demonstrate a left-hand side and a right-hand side of an equation. So the right hand side was that there was an originally a scene graph of this image where you had me and this. There was then a little like graph editor, came along and snipped this out and put it over here. So that's an agent. Okay. So we have so far two models. We have one that is the scene graph generator, which looks an RGB image and generates the correct scene graph or a scene graph, maybe incorrect, but we're going to learn, it's going to be parked over time. And then we have a second, is this snipper, this like little graph guy and he's going to be an RL agent. Okay. So, that's the right-hand side of the equation. On the left hand side, we're going to have the action of me. I'm an agent in this world and I am going to move this cup over here. And then we're going to take the scene graph.

**Cinjon (00:54:42):**
So now we have the scene graph. It's the same thing, right? It's, I moved this cup from here to here. So we had this, now it's like this. So I live in an embodied world. This cup is an embodied thing in that world. My action in that world led to a scene that then we took the scene graph over, that's the left-hand side. My claim is that this is an equivalent relationship. And so you have three agents. One is a scene graph generator. The other is the snipper, the graph walker. And one is me. And if you can get this optimization problem to work, to generate all three things at the same time, you can build the robot agent, the robots scene graph generator, which is its understanding of the world and the graph snipper, which is really not important, but it's necessary to make this work. You can generate them all the same time.

**Josh (00:55:45):**
That's really cool.

**Kanjun (00:55:46):**
That's a really interesting idea.

**Cinjon (00:55:47):**
Yeah. So it'd be, I guess like unsupervised self-service, whatever word you want to use, way of getting at both the RL policy and the scene graphs.

**Kanjun (00:55:59):**
Cool.

**Josh (00:55:59):**
Yeah, that seem really interesting. I like that a lot intuitively, as a way of thinking about what our actions, if you think about, Oh, if I want to fill up my water bottle, this is what I do. I go to the thing and now it's filled, now it's changed. And like those two scene graphs are different. Like I know how to go from one to the other. So I had to learn that action somehow right?

**Cinjon (00:56:18):**
That's right. Yeah, exactly. This setup needs to understand. It has some sense of the ego of the robot being relative to the scene graph. It's a little hazier.

**Josh (00:56:30):**
Yeah. Yeah. That's really cool.

**Kanjun (00:56:33):**
That's really interesting.

**Josh (00:56:34):**
Thanks for those ideas. I hope someone takes them and does something with them. Are there any other, like things that you feel like made you a much better researcher or that you've learned over the past few years and wish you knew earlier?

**Kanjun (00:56:44):**
That might be useful for other people?

**Cinjon (00:56:46):**
I will say that I was surprised at what the actual feeling of being a researcher ended up being. I think one of the brain, I didn't really, it didn't click yet what I was doing wasn't, I'm not seeing the output wasn't researched, but what I was personally doing, didn't feel like that. And I think it really wasn't until after I had completed my second, mostly solo endeavor in this, that I thought like, Oh, that's what that feeling is. That's what I see. And this is hard to convey actually, but people who are more senior, they've said, okay, I see, Oh, this is what doing, this is what, like being a researcher, that mindset really is.

**Kanjun (00:57:32):**
How would you describe the way it feels relative to how it felt before?

**Cinjon (00:57:40):**
It's very much that like old cobbler thing about how you pay a cobbler $50 to put some paint on the shoe, but like because he knew where to put the paint. I don't know what example to use with that. I went to the cobbler today. I would not have known how to repair my shield, but he knew exactly how to repair the shoes. They got done really fast. But I guess what I'm saying is that there's a sense of, Oh, these are the questions that I should be asking, or these are the hypotheses that make sense. This is the direct line to the question. And this is why it's important. What are the important problems and what are the right questions to ask about them?

**Kanjun (00:58:22):**
It's interesting. One of our team members, Abe, talked about how a really good way to see your own improvement as a researcher, is to write research notes every month or so. When he used to be preparing for his meetings with his PI, he would write a research note that took a day or two. And it's basically, why did you do this research? What did you do? What do you find? Why do you think it's meaningful? What's next? And it's interesting. He felt like when he went back in time and read his notes from a year ago or two years ago, it became very clear. The questions he's asking, make a lot more sense. And he has a much clearer path toward what is interesting. And what's not interesting.

**Cinjon (00:59:02):**
Without question. Yeah, I have the same thing. It's a different structure, but it's roughly the same thing. And I've experiment logs for all of the stuff, the longer experiments. The longer projects I've done, but then I also have these like hypothesis logs and the hypothesis these logs are meant to be, like I'm writing down roughly, actually the same thing all the time, it's not roughly, it's background hypothesis, variations, references, that's it. And it's just meant to convey the idea to myself and to someone else. But you see development of those and you're like, Oh, these are way better questions then asking them.

**Kanjun (00:59:40):**
Thank you for listening to Generally Intelligent. We love feedback and questions. So please feel free to ping us on Twitter at Kanjun and at Josh Albrecht or email us with any ideas or corrections. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify, for your favorite podcast app. Thanks very much. And we'll see you next time.

