---
layout: post
title:  "Generally Intelligent #2: Sarah Jane Hong, Latent Space, on neural rendering & research process"
date:   2021-01-06 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe id="podcast-embed" src="https://anchor.fm/untitled-ai/embed/episodes/Episode-02-Sarah-Jane-Hong--Latent-Space--on-neural-rendering--research-process-eol1vq" width="100%" frameborder="0" scrolling="no"></iframe>

Excited to release our second episode of Generally Intelligent! This time we’re featuring [Sarah Jane Hong](https://twitter.com/latentcodes?lang=en), co-founder of Latent Space, a startup building the first fully AI-rendered 3D engine in order to democratize creativity.

Sarah co-authored [Low Distortion Block-Resampling with Spatially Stochastic Networks](https://arxiv.org/abs/2006.05394) from NeurIPS 2020, a very cool method that lets you realistically resample part of a generated image. For example, maybe you've generated a castle, but you'd like to change the style of a tower - you could then resample that tower until you get something you like.

**Highlights from our conversation:**

- What it was like taking classes under Geoff Hinton in 2013
- How not to read papers
- The downsides of only storing information in model weights
- Why using natural language prompts to render a scene is much harder than you’d expect
- Why a model’s ability to scale is more important than getting state-of-the-art results

<br>
*Below is the full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
<!--more-->
<br />

### Transcript
**Kanjun Qiu (00:33):**
Sarah is one of the co-founders of Latent Space, which is a startup that is building a deep learning rendered 3D engine in order to democratize creativity. Sarah's recent paper at NeurlPS 2020 is called Low Distortion Block-Resampling with Spatially Stochastic Networks. This is a method that allows you to realistically regenerate part of an image, which is actually really cool.

**Kanjun Qiu (00:54):**
For example, maybe you've generated a castle, but you'd like to change the style of a tower. With their new network architecture, training procedure, and re-sampling algorithm, you would be able to re-sample that tower until you get something that you like. In their paper, they have examples where they re-sample building architecture, they change someone's hair, they add glasses to photos of faces. It's really cool. The results are really incredibly realistic, and I encourage you to check it out.

**Kanjun Qiu (01:21):**
Sarah has had a really unique path into research. She was the head of product at an NLP startup called Sonar, and she was a software engineer and product manager before that. She's incredibly brilliant. So, her work in deep learning and VR led her to receiving an Oculus Launchpad Scholarship and also an XR Studio Fellowship from Mozilla.

**Kanjun Qiu (01:40):**
Welcome. Sarah, we're really happy to have you here today. Just to get started, we're curious about how did you initially get into research?

**Sarah Jane Hong (01:48):**
Yeah, for sure. Also, thanks for having me. Really excited to talk about this stuff. I think long story short is that it actually started all the way back in undergrad. And I was really fortunate enough to have gone to the University of Toronto, taking classes by Geoff Hinton, where he was teaching neural nets really early on. This is back in 2012, 2013.

**Sarah Jane Hong (02:06):**
I didn't realize it at the time, but what initially got me interested is I felt like software was eating the world, and I felt like AI was an extension of that. It seemed like there was going to be some sort of intelligent AI that was going to happen, and I wanted to understand that. I felt like it was uncovering a piece of the universe. To me, that's where it really started to begin. And just how simple backprop was and cross entropy, how well that worked.

**Sarah Jane Hong (02:31):**
I had a bit of a pause between graduating and then going back into research. I really wanted to learn software engineering. And then, I got into product management. I was a head of product at this startup at the time. We were focused on conversational AI. That's when I started getting back into NLP, and that's what sparked this knowledge again, like curiosity. And so, that's where I began to go deep into research and started reading papers and implementing things.

**Kanjun Qiu (02:58):**
You mentioned taking classes under Geoff Hinton, which is quite interesting, back in 2012, 2013. What was it like back then? What were the assumptions that you and he had? Have they panned out?

**Sarah Jane Hong (03:10):**
I remember my first class, Geoff Hinton was basically making the claim, which I still believe is true, that for instance, it's basically impossible to write these types of programs where you literally have to describe... You have a task like classify all these dog types, classify all these numbers.

**Sarah Jane Hong (03:31):**
His first example was actually on MNIST and classifying numbers and how difficult that was. It's really quite hard to explicitly write every line of the program of how exactly, like all these rules, and that this approach, neural networks, some sort of learned approach, was basically the solution for that. So I've always thought about it as neural networks is a way to find the correct program within the space of programs of how to solve things, and that things like transformers are probably just an example of something larger that is more general purpose. But this type of learning technique is quite simple, yet works really well.

**Sarah Jane Hong (04:12):**
On a side note, I wasn't really exposed to the anti-neural network philosophy. And I think that's more of a bias based on the types of professors you have. I learned that later on in life, a lot of the things you think are true are actually heavily biased in the opinions of their teachers. And so, to me, I didn't realize how neural networks were quite taboo. To me, I just thought they were the default.

**Kanjun Qiu (04:45):**
Fascinating.

**Sarah Jane Hong (04:45):**
Yeah, and I think they had won ImageNet, which he mentioned nonchalantly, like, "Oh, okay, sure." I didn't realize it was a big deal until many years later. I was like, "Oh wow."

**Kanjun Qiu (04:58):**
That's super interesting. What was one of your biggest mistakes as a researcher?

**Sarah Jane Hong (05:03):**
I think the thing that I got wrong really early on is figuring out how exactly to read papers. It's not how you would normally think about reading papers. It's actually like how to not really read the paper unless you really have to.

**Sarah Jane Hong (05:20):**
Step one is probably you read the title, you read the abstract, you probably look at the first figure, and you don't have a completionist mindset. You don't read the full thing. I used to try to read the full thing in so much depth, I would stop at every sentence or every section and look other things up and go into this deep hole of reading. It's really important to not go deep on the paper initially. Don't really read it.

**Sarah Jane Hong (05:48):**
After that, I think it's effectively to see if there's other resources about it. And the important thing about this is that, especially early on, understanding the signal from the noise. And so, I think there's a lot of noise in machine learning research, and it's really important to see where the dust settles. I think it's really important to use other resources, whether it be blog posts or re-posts, any sort of talk that the authors have given that's online, going into those first, before going into the paper.

**Sarah Jane Hong (06:20):**
And so, for me, being able to implement the idea myself really quickly, like an MVP, or if there was an open source repo, running it myself, observing the trending dynamics and what was happening, I think that was really important. I learn a lot better when I'm able to do the thing, rather than read the thing. It's very much that first approach. And so, I think through doing that, then you basically circle back to the paper and have this back and forth process. And then, eventually, you go through the entire paper, but now it's really rare for me to go through the entire paper on the first pass.

**Sarah Jane Hong (06:59):**
And so, when I read a paper, I don't fully consider myself having read a paper until much after, whereas before, it would be within the hour type of thing. I think the second thing that I learned is, from a research perspective, it's a little bit more on the software engineering side, which is setting up your benchmarks and tests, properly setting up experiment design, ensuring what exactly your benchmark is, what exactly are you comparing it to, and then only moving one thing at a time so you can actually verify what exactly caused this effect.

**Sarah Jane Hong (07:38):**
And this is more a philosophy, but I think it's really important, which is it's more psychological actually, which is basically whenever you are doing research, you want to see this idea be true because you believe in it so much. That's why you're pushing forward on it. And I think the whole research process, you have to be your biggest skeptic because every hint of sign of life, you're like, "Ah, it works."

**Sarah Jane Hong (08:06):**
But you should really be skeptical and try to evaluate things in every possible way to really verify that. That was a hard thing to get into the mentality of, because it's so easy to see things and be like, "Awesome, it worked," and then check on things later and be like, "Wait a second." Yeah.

**Kanjun Qiu (08:28):**
Why was reading too many papers versus really implementing the code yourself bad? What made you realize, "Oh, I'm spending too much time just reading papers and understand the concepts, and I'm not enough in the weeds?"

**Sarah Jane Hong (08:40):**
A lot of ML research is still quite empirical. Justifying the correct learning rate optimizer is still very difficult, or various types of optimizers and things like that. And so, for me, it still boils down to empirically what you can or can't verify.

**Sarah Jane Hong (09:03):**
And so the math can check out, but if it doesn't work, then we have an issue. Or more so, rather if you can choose something to work, then you can dive deeper into understanding why or why not. Perhaps that's a little more controversial.

**Josh Albrecht (09:17):**
Yeah, actually, we were both talking about a paper a few weeks ago and you were just like, "Oh, let's just pull up the notebook and work through the notebook." Rather than even reading it, I think, your instinct is to go straight to the working code, which I actually found to be a really good way of actually understanding what was happening inside the app.

**Sarah Jane Hong (09:34):**
This was the cellular autonomy test of, yeah. This is just another example in the list, if there's some resource. In this case, it's amazing that there was a code lab notebook from the author, which was great. The code doesn't lie, basically. And to me, it's a lot more fun being able to interact with things, is if you change certain parameters or quickly just add the different type of loss, or change the architecture in some way, you get a faster feedback than, say, reading five different papers and then realizing, "What if we combined this bit and this other bit?" I definitely think there's a balance, though. It's more of a ordering of things.

**Kanjun Qiu (10:18):**
Are there any tips or hacks or tricks that you've developed over the years that you feel have really improved your effectiveness as a researcher?

**Sarah Jane Hong (10:25):**
I think there are a few major areas where I feel that I've learned a lot of tips as a researcher. I think the first one is more on an individual level, which is keeping track of notes and papers and things like that, and so for me, I'm using Miro, which is this collaborative, white boarding software, has been really useful. I'm a lot more of a visual person, and so I like to take screenshots of various talks, snippets of papers, sometimes even code snippets, and put them on this virtual whiteboard, essentially, so that I can collectively approve things and see how ideas connect to other ideas. I think that's more on an individual level, which I find really helpful. The other area is, I used to use TensorBoard a lot for experiments, but then we started using Weights and Biases, and I think that was actually a really big change.

**Sarah Jane Hong (11:24):**
It was very simple, but TensorBoard, you have to host it yourself, and with weights and biases, you effectively have a automatically served TensorBoard, but it was actually even better than that, which is that I was able to do custom visualizations and organize things in certain ways that were really useful for me. I didn't feel held back by the tooling. I felt like the tooling was helping me move forward. It really helps with this notion of reproducibility. It's really useful to be able to trust a tool like this, because I log literally everything, all the configs, log every single metric possible, all the types of visualizations. I do a lot of visualizations and metrics during training, as opposed to after. People are usually only looking at charts, but at least here at Latent Space, we look at both qualitative and quantitative types of metrics, which are important and having Weights and Biases really supporting our types of workflows been really useful for that.

**Sarah Jane Hong (12:27):**
And in particular, we are actually working quite collaboratively with them on their reports feature, and that is actually at the same time we were writing this paper. We're basically saying like, "Reports are awesome. This report is the draft of our paper, essentially. It's the one thing we're going to look at, we want it to be collaborative," before, they were not collaborative. The reports were just a very simple dashboard, but I think that really changed it for us to be able to do collaborative research. That was a really big hack from a researcher perspective, because now we were able to share results very concisely and so, as opposed to speaking your result, you can literally go through your result, everyone can see and verify and also reproduce exactly what you did and build upon that. I thought that was a huge game changing experience for us [crosstalk 00:04:17].

**Kanjun Qiu (13:18):**
We should adopt that. Actually, I think it would be great to give people a slight overview of your paper, stochastic spatial networks for low block distortion. It is going to be at NeurIPS 2020, so in two days, and it is a very interesting, compelling paper with a lot of really cool demos, so tell us a little bit about the paper.

**Sarah Jane Hong (13:40):**
The whole point of our paper is that we have at generative model, and typically generative models, you have a particular latent code that then is able to generate the entire image. And in particular for us, because we're building a neural rendered engine, having the whole scene just be one latent code doesn't necessarily make sense. And I think having that type of practicality really helped our research in the sense of, if you think about the world in terms of go blocks, there are certain chunks of the world, and being able to associate a latent code with each chunk of the world that really enables people to just certain areas of the image without having to regenerate the full image, or apply other methods that require human supervision, such as having labeled segmentation maps, to dictate on a pixel level exactly what to edit or what to generate and things like that.

**Sarah Jane Hong (14:37):**
And it's a little different. We contrast it with inpainting because inpainting is actually pretty interesting, and the differences that we still want to generate images that are on the manifold of possible realistic images, or imaginary images that to us, as humans, feel plausible as to what we want. So it's not going to be rigid to this underlying grid. Whereas inpainting, it can only change within the bounds of where you specified. We have some examples in the paper here, where if you're adding glasses or changing the hair for churches. If you're, for instance, changing the towers, there are certain other things that might change in order to make the image still look plausible, but it is within the reasonable radius of where the change is in the image.

**Josh Albrecht (15:22):**
Earlier, you mentioning that the idea is simple, and so I'd love to hear the simple description of how the thing works.

**Sarah Jane Hong (15:28):**
The simple version is, if you have an image and you change a particular part of it, you want that part to change and things far away from it not to change.

**Josh Albrecht (15:38):**
With the particular loss or micro-organization that you guys had. How does that thing work? I get the feeling that the algorithm itself is not actually that complicated.

**Kanjun Qiu (15:46):**
It seems like, from the paper, that the whole image is allowed to change, so how did you actually restrict it?

**Sarah Jane Hong (15:52):**
The initial thing, it was a research thing that I learned, which is do the simplest, dumbest thing. And if it works, then that means you're onto something, and then you can refine from there.

**Josh Albrecht (16:06):**
Can you say a little more about the complicated version or a simple version that you had at first?

**Sarah Jane Hong (16:12):**
Martin Arjovsky, which is one of our collaborators on the paper, what I really admire about him is his ability to simplify. And when you think you've simplified, there's more to simplify. He's really ruthless about that, and I learned a lot from that process. And so for instance, our initial regularization was literally just a binary mask, where it's literally just a square for the particular latent code that was changed and everything else. And we compute just the absolute difference of if anything changed in the area where it shouldn't change, versus only changed within this square area that we changed within the latent block. It was really simple and there's so much you can improve upon that. It worked better than we thought, because you would think that having a loss like that, you would have grid artifacts, because you're literally just doing an absolute difference between this square mask, which doesn't really make sense, but it works.

**Sarah Jane Hong (17:13):**
And I think that's an interesting research learning, which is, start with something that's really simple, and to, you may seem really dumb, but it's the complexity that kills you. And so having that checkpoint was really important, and that's when we were like, "Okay, we should probably write a paper about this." I think we updated the paper basically to a different loss, which is something that makes a little more sense, which is a radial fall off. And so, you want to penalize changes that happen further away, more than things that occur closer to the area of change. And so, I think that's what made potentially it harder to read in the paper, because all of the math became more difficult once you add a radial fall-off compared to a very simple, "If this block is not the one that change, then it's penalized-"

**Sarah Jane Hong (18:03):**
... block is not the one that changed then, it's penalized. But the idea is really simple. You start from that and then you realize, okay, we're also operating in pixel space. We can improve on that and move things into the more perceptual type of loss. But we didn't get to do that. I think that's where earth movers distance is a potential improvement there. So I think there's a lot to build up from this, but I think that the core of it is quite simple. Which is that things that are farther away from what you change should just be penalized more than things closer to you.

**Kanjun Qiu (18:33):**
When you were writing this paper, what are some of the things that you tried and expected to work, but they didn't work?

**Sarah Jane Hong (18:38):**
I feel like everything we tried worked.

**Josh Albrecht (18:40):**
Wow. That's a weird answer. Can you say more about that?

**Kanjun Qiu (18:45):**
Wow. Tell us about the process there. What were you expecting? And then, what were the things you tried, and then that they all worked?

**Sarah Jane Hong (18:53):**
We tried the dumbest thing and it worked, which was the absolute difference between the areas that should be the same versus the areas that should not be the same. And then I think everything after that was just an improvement in terms of the ideas. I think we started with a floor that was already, we thought was not good. But the fact that it worked, it made everything else easier. If something's too complicated, get rid of it.

**Josh Albrecht (19:23):**
At least in the paper you mentioned that you spent a total of $2,000 on the compute because you were using only the pre- trained StyleGAN2, I think. Right? As the network that you're building off of. How did you guys decide to do that? And has that kind of method continued to be fruitful going forward? What was that experience like?

**Sarah Jane Hong (19:42):**
We're a startup that also does research, so we have funding, but it's not to the extent where we can just blindly scale things up. And so I think that was actually a thing that came out of the constraints of our situation, and so we had to be resourceful and creative. I think the thing that I learned a lot from this process is that transfer learning is really good, especially for iteration time. Because you get feedback so much faster than if you were to, say, train for days or weeks and things like that. So you can iterate on ideas on a timeframe that is 10 or 100 times faster than otherwise. I have talked to some people at other labs, they run an experiment on their plaques, like shared cluster and fight for time, seven days later, or a month later they get results.

**Sarah Jane Hong (20:34):**
And they're like, it's pretty painful if you have a bug, and XYZ types of problems. So I think there's two points. One is that transfer learning is really good for fast iteration time, which I think is really crucial for research. I think the second thing is that there's the critique that your idea just might not work because of using transferred weights. I think that can be true some of the times, but I also feel that if your idea is robust enough it should work with transfer learning. I'm sure there are cases where it would be ideal not to, and so you basically train a new base, and then iterate on your experiments from that shared base. But for us, it just made sense to use the StyleGAN2 weights in this use case.

**Sarah Jane Hong (21:20):**
I'm sure people prior to this paper's results would say, "Oh, but StyleGAN is on the one latent code and you're now changing the representation by having multiple latent codes that doesn't make sense to do. That definitely works. And if you were to train from scratch, I'm sure it would work too. Which we have done, but it's just expensive to do. I think it's something to definitely consider if you're running into certain issues, but it's not the first thing I would go to. When you think about image classification or all of NLP, everything is focused on transfer learning and fine tuning. So you don't really see that much from the generative, like image generative modeling in particular. But I don't see why not. And so for us, what we did in the paper, that's what we do internally as well.

**Kanjun Qiu (22:06):**
Back to the latents. One thing I was wondering was, how were you actually able to change the latents in a way that fit with the rest of the image and made sense?

**Sarah Jane Hong (22:17):**
Changing the latents, we call this the re-sampling process. And so it's rolling the dice. It looks at the surrounding latent codes and it says, oh, I'm near the top so I should probably most likely generate something like a tower here. Versus, I'm touching the ground, so I most likely should generate a wall or a door, a gate or something here. That's the idea there. Another part that's actually interesting with this is that thinking about the latent resolution in relation to semantic features is interesting. If you think about a typical GANT, the latent resolution is just one by one, because it covers the full image. And there's a spectrum between that and all the way down to the literal pixel as the latent resolution.

**Sarah Jane Hong (23:01):**
And you want to basically choose a latent resolution that is coarse enough, two by two or four by four, but that covers a good chunk of semantic information. So if you think about a face, you'd probably want to think of things in the four by four latent resolutions. As opposed to, let's say, just to be extreme, like for the thought experiment, like 128 by 128 latent resolution. Because then you're not really capturing anything within the latent code, it's way too much on the pixel level, like low-level features. You want it to be a little bit higher. So I think that's actually an important parameter to think about.

**Kanjun Qiu (23:35):**
You were working on this startup in NLP, how did you get from NLP to here?

**Sarah Jane Hong (23:43):**
Yeah. For me it was always about understanding. And in terms of vision, I think what we're working on at Latent Space, basically neural rendering, a really big component of that is actually a semantic understanding. Language is a really useful tool that we've developed as a species. I think there's some combination of vision and NLP, which is a good combination for this type of neural rendering work that we're focused on now.

**Kanjun Qiu (24:10):**
Are there any hunches or theses that led you to the work you're doing now?

**Sarah Jane Hong (24:16):**
I think the thing that has changed for me is that I don't think everything can be stored in the weights of a model. In close partnership with that idea is also having a model that is extremely large hosted on a server. Before, I think we were thinking about things more so on device, and having it be able to generate these things. Now we've shifted our mindset more towards the large server base model, that's a change in the dichotomy there.

**Kanjun Qiu (24:49):**
The first thing you mentioned was that you no longer believe that all the information can be stored in the weights. What led you to the shift toward believing that?

**Sarah Jane Hong (24:58):**
Yeah. I think in the limit things can. Just from a practical point of view, we definitely want to continue to be scaling the model up. However, if you combine this with basically retrieval augmented techniques, you can achieve similar performance on a smaller model. Which means that you have more gains to continue scaling up, so combining both I think it was going to be really powerful. How this ties back into what we're working on here at Latent Space is that one way is to think of it as we have some sort of oracle. And if you were to describe a particular scene, having it be able to actually generate a scene that matches closer to what you are thinking about, it's a really difficult task.

**Sarah Jane Hong (25:48):**
And so we actually have a funny example of Wolverine as our canonical use case. Because you have wolverine the animal, but you also have Wolverine the actual X-Men character. And Wolverine, the X-Men character, also has multiple ways that he can be generated, so to speak, basically visualized. Then there's the comic book version, there's people sketching him, him as a toy, him as Hugh Jackman. So there's a lot of variety in how exactly you visualize Wolverine. And when I say visualize, you can think of it as the model generating it. But we understand that this is Wolverine, the person in X-Men universe. And so from a pixel level they're very different, but from a semantic understanding level they're the same. They're all very close together. For us, that's really important from the neural rendering perspective. I think being able to understand that.

**Kanjun Qiu (26:44):**
That was a really good example.

**Josh Albrecht (26:46):**
And one thing you mentioned is that you have had things that didn't work out in the past. What can we say about some of the unpublished research failures that you have experienced?

**Sarah Jane Hong (26:56):**
Yeah. Something that we tried early on was a two-step training process. It's not necessarily new. There's a lot of research on this at least five years ago. Having a autoencoder as the first step and then, in the second step, learning the representation of the bottleneck, but we were just not able to get that to work. And then VQ-VAE came out and then Jukebox. So definitely it does work, but I think we just didn't push on it as much. And I don't have much to say on why it doesn't work, why we failed. All I can say is that we weren't able to get it to work, but intuitively, it made a lot of sense. It's a lot easier to learn from a more compressed representation than say directly from pixels.

**Josh Albrecht (27:43):**
So it's still an open question then.

**Sarah Jane Hong (27:45):**
It's definitely got to be a bug. It's got to be multiple bugs, actually. We have a similar setup like that now. And that works.

**Kanjun Qiu (27:56):**
Interesting.

**Josh Albrecht (27:57):**
One other question. I was wondering if you have any unusual opinions that people you've encountered don't seem to agree with. What are some of your controversial machine learning opinions?

**Sarah Jane Hong (28:07):**
Honestly, it depends on the lab, but I think most people are not thinking about scale. And to me, it doesn't feel controversial, but when I talk to people, that's when it starts to feel controversial. I think the scaling laws paper, for instance, should be a way bigger deal, but it just hasn't really resonated that way. Maybe it'll change. I'm not sure, but it just hasn't been getting the type of attention that I thought it would be getting.

**Sarah Jane Hong (28:33):**
It seems like getting state-of-the-art on some benchmark doesn't necessarily matter any more. What matters is how well your model scales effectively. That should be the metric now of how we evaluate new techniques, architectures and things like that. To capture that, obviously, it's not everyone can do this. And so maybe that's why it's not gaining as much, but I actually think it's a pretty big deal. For me, scale would be the controversial thing here.

**Kanjun Qiu (29:03):**
Interesting.

**Josh Albrecht (29:04):**
Kind of like really making it a first-class thing to consider. Like, does this scale? Yeah. I think that also probably goes back into your bias towards simplicity as well, in that things that are complicated are not going to scale. Like, if you have these 17 different networks with all these crazy hyper-parameters and special hacks that do something, it's just not going to ...

**Sarah Jane Hong (29:21):**
Exactly. For instance, based on the parallel, LSTMs could achieve the same performance as transformers; it's just they're the constant factor worse. And so it costs you a lot more in order to get an LSTM version of, let's say, GPT-3. It's possible. It's just not the winning version here. And maybe there's something that's going to be better than transformers. Maybe transformers are the answer. And it's not, they just scale way better. And I think they're a lot simpler.

**Josh Albrecht (29:51):**
Transformers are simpler than LSTMs?

**Sarah Jane Hong (29:57):**
I would say so, yeah.

**Josh Albrecht (29:57):**
That's interesting. I feel like that might be almost the more controversial opinion.

**Sarah Jane Hong (29:57):**
Really?

**Kanjun Qiu (30:01):**
I think people use transformers over LSTMs.

**Josh Albrecht (30:03):**
Well, I think people definitely use them over them. I'm just saying if you were to write it out, I think there's probably a lot more code that goes into typing out the transformer than typing out the LSTM, right? Kelvin was mentioning, actually, that there was a paper recently showing that you can take a multi-level transformer that's got feed forward layers and it's got the attention layers, and then you just shuffle all the layers, try all the different combinations. Like, what if we had all the attention layers and then all the feed forward layers? And it turns out some weird combination that's not just like stacking them works much better. So I thought that was kind of interesting, but ...

**Kanjun Qiu (30:33):**
Yeah, all attention layers first, and then feed forward layers, that's the winning combination.

**Josh Albrecht (30:39):**
We'll have to go look up that paper, then. But it kind of goes to what you're saying, though, in that it's really about finding things that are simple. Like the self-attention's a really simple mechanism and just finding these simple, scalable mechanisms are actually the really important thing. Are there any other controversial opinions like that do you have?

**Sarah Jane Hong (30:56):**
From the neural rendering perspective, there's just so much information within a given picture. And a picture is a thousand words. And more recently, there was the paper where a picture is 16 by 16 words. I think you can think about it from the other direction, which is a picture is millions of words or a very, very large amount because our world is just incredibly dense. If you just imagine a scene of, let's say San Francisco here, just the city's skyline, but there's all these different towers. There's buildings. There's the types of trees that are here, birds, the people that live in all these types of units. It's the Victorian ...

**Sarah Jane Hong (31:42):**
You can go all the way down to the granularity of Blue Bottle Coffee or even further down. How far do you want to take it? All the words associated with that? There's so many. And so I don't think it's necessarily just a thousand words or 16 by 16. But if you think about it from that perspective, every image is really quite dense in information, even if it's not fully visible.

**Kanjun Qiu (32:03):**
That's very interesting.

**Sarah Jane Hong (32:05):**
We want to be able to utilize all the information from humanity. It is effectively the internet, and that's how we connect this to how we're actually rendering things.

**Kanjun Qiu (32:19):**
Moving a little bit toward the end, are there any areas that you're really excited to see develop over the next few years?

**Sarah Jane Hong (32:26):**
Definitely the scaling law stuff. More people diving into that. We were doing something really similar about a year or year and a half ago. We weren't thinking about it from the perspective of AGI at the time, but it's more from the constraints of our compute budget. It's like being able to run smaller versions of our model and plot the curve and then slowly scale up and does it follow the same curve before we run the full fledge out thing? So I do think it could be applicable on a more tenable compute budget. I would love to see more papers and ideas trend in that direction, showing the power law curve there. It's a big ask, though. We'll see.

**Kanjun Qiu (33:10):**
I think that's really cool as a default, Josh, as a first-class concept to keep in mind for research. Are there any areas that you're interested in having outside collaborators?

**Sarah Jane Hong (33:22):**
I think the whole area of visually grounded language, I'd love to work with more people in that area. I think we like to think of what we're building as merging both the improvements and NLP and image generation. I think there's a paper called vokenization. And I think the idea that is closer to what we're thinking about, which is they have this whole thing called visual token, so a voken. That's similar to how we're thinking about our latent blocks in this block-like world as these vokens.

**Sarah Jane Hong (33:59):**
And so that whole area is really interesting to me. And I think the second area is definitely the retrieval work I was mentioning. And so basically, scaling retrieval up with these types of models, I think is nontrivial. And in our use case, we're really focused on image generation. And so thinking about things ... Image retrieval right now is really focused on pixel-level. And we want to be able to think about things from more, an idea semantic level. So closer to words. Going back to the Wolverine example. In terms of image retrieval, we don't fully want things to just be on the pixel level. So if it was a comic book rendering of Wolverine, we don't want to pull necessarily other comic book images; we would want to be able to pull images and other media as well in terms of what exactly is Wolverine, because there's a lot there.

**Sarah Jane Hong (34:56):**
We may want some things that are on the pixel level, but I don't think that's necessarily the core thing we're focused on right now. So thinking about retrieval from an image generation perspective is really interesting.

**Kanjun Qiu (35:05):**
Thanks so much, Sarah. This is really interesting and fun, and I feel like I learned a ton about both how to be a researcher and also about how to do a better job of generating images. And I'm really excited about your neural rendering work and we hope to see more work from you over the next few years.

**Sarah Jane Hong (35:22):**
Yes, definitely. Thank you for having me. This is fun to talk about.

**Kanjun Qiu (35:25):**
Thank you for listening to Generally Intelligent. We love feedback and questions, so please feel free to ping us on Twitter at @Kanjun and @joshalbrecht, or email us with any ideas of corrections. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify or your favorite podcast app. Thanks very much, and we'll see you next time.

