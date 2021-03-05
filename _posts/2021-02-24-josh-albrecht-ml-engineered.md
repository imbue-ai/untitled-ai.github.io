---
layout: post
title:  "Josh Albrecht: A New AI Research Lab"
date:   2021-02-24 09:00:00 -0700
category: machine-learning
tags: company

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>

---

Our CTO [Josh Albrecht](http://joshalbrecht.com/) was interviewed on [Machine Learning Engineered](https://www.mlengineered.com/)! Josh talks about pivoting from an AI recruiting startup to Generally Intelligent, touches on what we're working on now, and discusses how to think about creating a great research environment.

You can find show notes and links mentioned in the podcast on [Charlie You's blog post on this episode](https://www.cyou.ai/podcast/josh-albrecht).

<iframe id="podcast-embed" src="https://player.captivate.fm/episode/9e82a9eb-d823-42b8-b3a2-f49406ba101c" width="100%" frameborder="0" scrolling="no"></iframe>

**Quotes we enjoyed:**
> "I think that other primates or dolphins are actually extremely intelligent. And biologically, our brain is almost identical to that of many primates, though their language abilities are much more limited, and their ability to do symbolic reasoning is very limited. The interesting thing about intelligence is it's 99% there in the monkey brain. I think neural networks can approximate huge swaths of the neocortex and get very good correlations of whole clusters of neurons."

> "Machine learning is not really about automation. I think it's much more about augmenting people in the tasks they're actually doing, meeting people where they are, and considering the human side of the equation. That's something that's stuck with us now, and the way that we're thinking about our current work. ML and AI should be viewed from the lens of how they are serving human values, and how they are helping people do the things that they want to do."

> **Yann LeCun's cake analogy**: "The cake itself is unsupervised learning, the frosting is supervised, and the cherry on top is reinforcement learning."

> **On how curated datasets don't represent the real world:** "None of those images are a picture of a blank wall, or a picture of the grass or something, because no one takes a picture of the wall, because it's boring. But what do you see in real life? Most of the time you have a bunch of boring walls. The natural setting is, almost everything is boring, except this extremely long tail of things that are interesting."


<!--more-->

### Show Notes by [Charlie You](https://www.cyou.ai/podcast/josh-albrecht)
**02:15 Introducing Josh Albrecht**
- Originally got interested in programming via video games
- In middle school, he wanted to get a new computer and his dad told him he would pay for it if Josh worked through a 1000 page C++ book
- He actually did it and found it was more fun to program games than play them, had a part-time job in high school programming video games
- In undergrad at University of Pittsburgh, he wanted to do computational neuroscience research, but "it just felt like the field was being approached in the wrong way, or just didn't really resonate with me... I really wanted to know, how does thinking work? How does intelligence work? How does all this stuff actually work?"
- Started doing research with an AI professor instead, which "was a lot more fun." They published papers on machine translation and interfaces for understanding languages.

**06:35 Josh's first two startup attempts**
- "I love working on research... but is anyone really gonna ever use this tool that I built or read these papers? Probably not. And so I wanted to have a little bit more of an impact. And so that's how I got into startups."
- First startup was a cryptocurrency-like scheme for anonymous BitTorrent web browsing
    - Ended up getting a lot of users, but wasn't a very good business
- Started CloudFab after, which was a marketplace for 3D-printing
    - Matching people who want things printed with people who have printers
    - Later worked on predicting costs for injection molding with ML, which led to an acquisition

**09:15 The tech behind Sourceress, an AI recruiting platform**
- "One core thesis was that machine learning was going to have a huge impact on the world. We didn't know exactly how it was going to play out. But we were pretty sure this was going to lead to lots of automation... So we were looking around for things that are going to get automated... We've both done a lot of work on recruiting at our previous companies and had seen how slow and manual it was."
- Recruiting is a big matching problem between all jobs and all people
- They worked closely with hiring managers to deeply understand what they were actually looking for
    - eg. One HM might care about years of experience or credentials, another might care about skills only
    - "We built this huge ontology of different attributes and ways of thinking about candidates... Then we have models for each of these attributes so that we can quickly say, out of everyone in the world who has the attributes that this hiring manager is looking for?"
- Took over the whole process--candidate sourcing, outreach, and scheduling

**16:10 Pivoting from Sourceress to Generally Intelligent, an AI research lab**
- Sourceress worked really well, but they found it wouldn't be able to scale as big as they wanted to
- Found lots of poorly aligned incentives in the recruiting industry
- "Machine learning is not really about automation. I think it's much more about augmenting people in the tasks that they're actually doing and meeting people where they are and considering the human side of the equation. And so that's something that's stuck with us now and the way that we're thinking about our current work. ML and AI should be viewed from the lens of how they are serving human values and how they are helping people do the things that they want to do."
- Had been considering a pivot to AI research since their seed round, but there were too many open questions ("How can this be a business?", "How can we make meaningful progress on this?")
- Returns to more general AI is so huge that it lends itself well to venture backing

**23:50 How Josh defines "general intelligence"**
- "Something that's capable of solving a more broad range of tasks without having an ML engineer come in and do a bunch of fiddling for the specific task."
- "For the set of human relevant, economically important tasks, how do we get something that can learn those in a much more robust way?"
- On GOFAI vs ML
    - Was originally skeptical about the power of NNs, but came around as it became more clear that they can actually generalize
    - "I actually think that other primates or dolphins are actually extremely intelligent. And if you look like biologically, our brain is almost identical to that of many primates... Their language abilities are much more limited, and their ability to do symbolic reasoning is very limited. So I think the interesting thing for me about intelligence is actually 99% there in the monkey brain, in a primate brain... I think neural networks can approximate huge swaths of the neocortex and get very good correlations of whole clusters of neurons."
28:35 Why Josh thinks self-supervised learning is the current most promising research area
Likes Yann LeCun's cake analogy: The cake itself is unsupervised learning, the frosting is supervised, and the cherry on top is reinforcement learning
"These self-supervised [algorithms] allow us to learn patterns from data, without any human supervision at all, just seeing what patterns exist in the natural world. And so I think that's a very powerful, very important part of it."
Self-supervised approaches now almost as good as supervised approaches
Curated datasets don't represent the real world
"None of those image are a picture of a blank wall or a picture of the grass or something because no one takes a picture of the wall, because it's boring... But what do you see in real life? Most of the time you have a bunch of boring walls."
"The natural setting is almost everything is boring except this extremely long tail of things that are interesting."
36:15 What Generally Intelligent is working on now
Simulated environments
Amazingly realistic renderers and simulators are available now
"One of the cool things about a simulated environment is that it allows you to tune these knobs and turn up and down the level of detail so that you can ask: on this really simple dataset, things work, but as we make it more and more complex, how well does it work?"
Very excited about Sim2Real, transfer learning, domain randomization
Want to deeply understand how ML agents work on very simple problems
Object occlusion and persistence
Scene understanding and reconstruction
Learning the rules of physics: can you teach an agent to understand gravity?
Listen to the episode to hear Josh break down exactly what the research process looks like for this problem
Implemented Deepmind's BYOL algorithm and found it only works if there is batch norm layers, which they hypothesized is creating implicit negative samples within a batch.
See their blog post for more detail: https://generallyintelligent.ai/understanding-self-supervised-contrastive-learning.html
No final word on the topic, still lots of work to be done
59:20 How Josh thinks about creating an optimal research environment
They don't have the pressure present in academia to be constantly publishing, so they can think more long term
Can ask new questions instead of chasing SoTA on existing ones
Optimizing for deep understanding
Want people to pursue their own ideas no matter how crazy or contrarian they are
Psychological safety concept from Radical Candor
Thinking deeply about collaboration methods and internal tools
"Hot tub" daily meetings: one person goes in the hot seat and the entire team asks them questions about their recent work, can go very deep in a longer meeting
Project management: experimenting with measuring the velocity of things that are getting in the way of the team and removing them
Tools for enabling researchers to do more, faster while maintaining reproducibility
eg. "Auto Abe" hyper-parameter optimizer
01:11:35 The "why" behind starting an independent research lab
Feels very strongly that it is a very important thing for the future
"It seems much more likely for us to end up in a good spot if we're making intelligences that are similar to us and intelligence that we actually understand"
"Something that is really excited to support our values and do the things that people are excited to do and create material and emotional and intellectual abundance so that everyone can do what they're excited about. I think that's what we're excited about for the future."
Want to be very open about everything they are doing, actively blogging and podcasting
Starting to hire more, collaborate with researchers from other groups
01:17:00 Rapid fire questions
How far away is AGI?
Definition: 90% of economically valuable tasks that humans do now can be done with less than a million dollars of engineering cost
60-70% chance of achieving that in the next 10-20 years
For fun: lots of games
Books
Looking for a good neuroscience book
Radical Candor
Why We Sleep
Advice
"expect it to take a really long time because there's a ton to learn."
"One of the really cool things about computer science is that, you can understand at the electron level, everything that happens from pressing a key on your keyboard to a pixel showing up on your screen, and that's just so powerful and so cool. So don't be afraid to go down a bunch of rabbit holes or, spend your weekend reading a bunch of Linux man pages, it's worth developing very deep understanding for things. And it's possible to actually understand everything that happens in that thing. And it's not as hard as it seems, but it is hard."
Recent changed mind: "Strong opinions, weakly held" not a very good rule of thumb
Contrarian truth: Intelligence may turn out to be a lot simpler than people expect