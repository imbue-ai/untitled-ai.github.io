---
layout: post
title:  "Generally Intelligent #5: Katja Schwarz, MPI-IS, on GANs, implicit functions, and 3D scene understanding"
date:   2021-02-23 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe id="podcast-embed" src="https://anchor.fm/untitled-ai/embed/episodes/Episode-05-Katja-Schwarz--MPI-IS--on-GANs--implicit-functions--and-3D-scene-understanding-eqv4po/a-a4nupk9" width="100%" frameborder="0" scrolling="no"></iframe>

[Katja Schwartz](https://www.is.mpg.de/person/kaschwarz) ([Google Scholar](https://scholar.google.com/citations?user=mhOrpHIAAAAJ&hl=en)) came to machine learning from physics, and is now working on 3D geometric scene understanding at the Max Planck Institute for Intelligent Systems. Her most recent work, “[Generative Radiance Fields for 3D-Aware Image Synthesis](https://arxiv.org/abs/2007.02442),” revealed that radiance fields are a powerful representation for generative image synthesis, leading to 3D consistent models that render with high fidelity.

**Highlights from our conversation:**

🥦 the role 3D generation plays in conceptual understanding

📝 tons of practical tips on GAN training

〰 continuous functions as representations for 3D objects

<br>
*Below is the full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*
<!--more-->
<br />

### Some quotes we loved
> If you can generate something or if you can create something yourself like a prototype, it's nice because you can see as a program of what your model learned from the data. And on the other hand, if you reconstruct, it's way harder to see if there's a true understanding, or if it's just rapid juicing things. I guess why I favor this GAN approach because I feel that there's a lot of potential also for robustness. It's closer to this understanding. We humans can also think of different versions. 

> In our last project, we were actually thinking about using a VAE approach, just because of these nice stability properties. Then we decided against it because it meant that we would need to use posed images. Because if you want to reconstruct it, you need to know which pose it was taken from. And that's an advantage then again for GANs where you don't need to reconstruct exactly the same image.

<br>

### Transcript
**Kanjun Qiu:**
Katja came to machine learning from physics, and she's now doing 3D geometric scene understanding at the Max Planck Institute for Intelligent Systems in Germany. At this year's Merits, Katja presented her most recent work entitled GRAF: Generative Radiance Fields for 3D-Aware Image Synthesis. I encourage you to look at it because the visuals are beautiful and they simply can't be described in audio.

**Kanjun Qiu:**
Welcome, we're so excited to have you. I know you're working on 3D scene understanding now. How did you develop your initial research interests, and how have they evolved over time?

**Katja Schwarz:**
I think I was always a person that's been very interested in video, photography, basically imaging and also computer graphics. I was playing a lot of video games, but where I spent the most time on was actually designing the characters that you play with. I spent the most time in the beginning on getting my character to look super cool. This is where I started.

**Katja Schwarz:**
And then I majored in physics. At that time, I was getting super interested in physics simulations. And this is how I got into programming. Yeah, I wasn't super interested in programming from the beginning to be honest, but this is where I thought, "Oh, it's super useful." I continued with over classical image processing to computer vision, and since then I stick with it because I just really loved it. That led me to do a PhD in computer vision.

**Kanjun Qiu:**
What made computer vision interesting to you over all the other things that you looked at?

**Katja Schwarz:**
I feel if you visualize something right, and there's so much information in it, you can explain things extremely well if you just visualize them. You don't need a lot of words or complicated formulas. Sometimes it's the easiest thing if you just see it. That's what always fascinated me about images, and in general vision. This is what I really love about this area.

**Kanjun Qiu:**
What do you feel has been most interesting that you've encountered as you started thinking about visualization?

**Katja Schwarz:**
The most interesting part to me was what is needed to extract information from images, on the sides of humans but also in particular on the sides of machines. What do they need to do to actually get information out and to get a meaning out of it? Because what they get is basically just numbers. It's just pixels. How can you get an understanding in there? Is it even an understanding?

**Josh Albrecht:**
Do you have thoughts on that philosophical question?

**Katja Schwarz:**
If they really have an understanding or not?

**Josh Albrecht:**
Yeah, what counts?

**Katja Schwarz:**
I think currently we're not there yet. What we do have is task-specific. We tell the networks or the algorithm exactly what we want to do, and then it does exactly what we told it to. But it's difficult to be precise about, "What do you want?" When we work with these algorithms, we see all the time that they don't work as we expect. Maybe they do have an understanding, but it's definitely not aligned currently with what our understanding is in many cases.

**Josh Albrecht:**
When you build these networks, they don't always work like you expect. Are there any salient stories that come to mind of things where you're like, "Well I really expected it to work this way but it just absolutely did not?"

**Katja Schwarz:**
Some very well known examples are adversarial examples. In our area where we did 3D modeling, I was surprised how the model can learn to cheat. Sometimes it masks out things in generated images if it really doesn't know how things should look, then it places some weird white object in front and masks out things.

**Kanjun Qiu:**
Do you have some kind of metric internally for, "Oh okay, at this point I feel like models do understand what's going on in an image or what's going on in a scene?" How do you know?

**Katja Schwarz:**
We work a lot just with visualizations, and we just really look at what the model is generating. And the FID scores, all the metrics in terms of numbers, they are good to get a rough overview of a full dataset. How's my model performing? But I get the best intuition if I really look at what is it visualizing? Because for generative models, it's particularly nice because you can actually see what they learnt from the data.

**Katja Schwarz:**
But on the other hand of course, you need to look at a lot of examples. For me, I needed to develop quite some intuition to see how much failures, to just look at these images and get an understanding for what's actually going wrong here. And that took a while.

**Josh Albrecht:**
What are some examples of those?

**Katja Schwarz:**
Typical artifacts for example. For 2D images, you sometimes get these Tikal artifacts, where you have these small pixely areas in the image that looks a bit like a checker or pattern. In the beginning, I didn't really know where they come from. And there's a series of posts where they explain the way that you generate the images. If you are not careful, that can cause these patterns. Or in our case for the last project in 3D, we had small issues with resolution. We had some periodic patterns repeatedly.

**Katja Schwarz:**
It took us quite awhile to get an intuition what's going on there. It also depends a lot on how you generate images. For example, in our last project, we didn't use a conventional 2D GAN, we also use a fully connected neural network instead of the convolutional neural network. That also has an effect on the artifacts that you can see.

**Josh Albrecht:**
What was the story with the periodic patterns?

**Katja Schwarz:**
You'll find out that if you use these positional encodings together with fully connected neural networks, you can get a great boost in image fidelity. Because of the way that these positions and encodings work, you do get sometimes periodic artifacts or periodic patterns. And it was actually related to this.

**Josh Albrecht:**
How did you get rid of it?

**Katja Schwarz:**
It was having to sampling more points along the race, so basically to increase our resolution. Also that came at a cost of more computation. It was hard to fully get rid of it.

**Josh Albrecht:**
It was a little bit bruised for us, maybe.

**Katja Schwarz:**
I think the boost from these encodings, it was just too great to just not use them.

**Kanjun Qiu:**
I noticed that with your paper so far, you've been quite interested in how do we find 3D representations that are good representations of an image or of a scene? How would you describe your current research interests?

**Katja Schwarz:**
I'm really interested in 3D generative modeling, but the most important part for me, it is to make it controllable. The existing generative models, they do a great job at generating photo-realistic images and making them look super real, but it's very hard to really do something with these images. And you really want to get more control. You maybe want to change perspective. You want to maybe change a part of the image. You just want more control.

**Katja Schwarz:**
And this is the main focus of our research and also of the previous project before this year's NeurIPS one. We were also interested in generating controllable scenes. You could generate different objects and then rotate them or translate them. But the first thing we noticed is that it's very hard to get supervision for this, because 3D supervision is usually not readily available.

**Katja Schwarz:**
And this is why we thought it would be great if we could just learn it from images. Now we had a lot of advances in differential rendering. It really seemed a good time to start this learning just from images and learning from 2D supervision.

**Josh Albrecht:**
Can you speak a little bit to the story and the origins and everything for the first paper? How did it come about? Was it really inspired by that? You just coded out the whole thing and it worked as expected, and you were like, "Great, we're done." Or did this evolve from another project?

**Katja Schwarz:**
It was actually my first project in the PhD and I came there and joined the project. We had this idea that it's probably super difficult to learn to model 3D objects directly only from 2D images. The idea was to model them with easy geometric 3D shapes. And by modifying these 3D shapes, for example, by rotating 3D cube or 3D sphere, you tell the model. It should also correspondingly rotate the object in the image.

**Katja Schwarz:**
And in this project, we weren't so much interested in getting the correct 3D model, but we just wanted to have a correctly transforming generated image. That was the main idea there.

**Josh Albrecht:**
Could you give us a brief description of what that paper was about and how the model worked?

**Katja Schwarz:**
The main insight was that it's probably very hard to directly model the 3D object, and that it's enough if we can generate an image that transforms realistically. The idea was to model a simple 3D object that corresponds to a more complicated rendered object. Modifying this 3D primitive, we were able to transform the more complicated object, the rendered object accordingly.

**Josh Albrecht:**
It was really cool work. Output photos look pretty good and you can actually control them. And it seems like they move in a reasonable way, which was really cool. It's multiple objects. You can have three different cars, and you can rotate them and translate them around. Does the model need to know how many objects are ahead of time during training? Or how is that part handled?

**Katja Schwarz:**
The model doesn't need to know how many objects are in the scene. And [inaudible 00:09:15] was important to not have this constraint to not need to specify, like now we have two or three objects. Ultimately we can decide how many objects we want to generate, but we want it to be able to train with data with different amounts of objects to give the model the opportunity. In the model we randomly mask out some of the objects, thereby we always generate multiple objects, but in the image there will be more or less a random number.

**Katja Schwarz:**
We do make the assumption that random masking is correct, that all numbers of objects are equally distributed, but we don't assume any specific number.

**Josh Albrecht:**
Did it actually start from the spheres and cubes and that transformation, and then the point cloud stuff was added later?

**Katja Schwarz:**
Exactly. We started from spheres. In the beginning we even generated images with spheres. We usually have this philosophy in the group that you need to start from a super simple setting, especially in GAN training. There is no other approach to making it really work because these models are so tricky to train from what I've experienced.

**Katja Schwarz:**
It's just a really good approach to start very simple and then increase complexity very slowly, and step-by-step. For this project, it was also very tricky to actually get training stable and all these different components to act together. That was one of the biggest challenges.

**Josh Albrecht:**
Can you talk more about that, about the challenges of that?

**Katja Schwarz:**
The biggest challenge is that it's very hard to see what is really going wrong, because you don't get some score that is really bad, or you don't have a good metric to measure what's the problem. A lot of GAN training relies on intuition. You're taking models readily work, and then you try to modify them because you always want to have this balance between the generator that generates your images, and the discriminator that is trying to detect what's real and what's generated images.

**Katja Schwarz:**
And you need to make these models approximately balanced, so that one doesn't learn much faster than the other, because that will get your training to collapse. A fair amount of engineering goes into these models, and just to see that they're balanced and that they act well together.

**Josh Albrecht:**
Did you feel like at the end of the project, you still had a good grasp on, and it's like, "I can make these things do what I want." Or is it more like, "Ooh, good thing we got that working. I don't know if I'll make it go any further."

**Katja Schwarz:**
In this type of setting that we had, things were really working quite well. We experimented with very simple toy cars on uniform backgrounds. We even recorded a real wide data set, but very simple one with also uniform backgrounds, and some fruit that we put in front. And it was very basic geometric shapes. But in this setting, I would say the model worked as we expected. And you could see that the transformations that we did really corresponded to what should happen in the images.

**Katja Schwarz:**
With this project, it was very hard to scale up to low complex scenes, because ultimately it needed to disentangle the objects in the scenes without any supervision. And then also at least get a 3D understanding of each of the individual objects, without any 3D knowledge. That was very challenging.

**Josh Albrecht:**
That's a nice way of getting around. It seemed like one of the failure cases was still there. It would sometimes lump two objects together or lump it into the background or something like that. But it didn't happen most of the time, I think. Right?

**Katja Schwarz:**
Yeah, yeah. No, that was definitely some failure cases, but usually it doesn't tangle the objects correctly. And I guess it's also a reasonable failure case because you actually never define what an object is. That network needs to learn by itself. What is an object, and how is it defined. If you go to my abstract case, it's sometimes not that obvious. If you, for example, think of a vase and you have flowers in it is like, "Are the flowers one object and the vase is the other one? Or is it actually one object together?" That's on a higher level. It can be quite ambiguous and it's a difficult task to learn unsupervised.

**Josh Albrecht:**
It is very unclear what is an object? Is the whole set of flowers, or the vase and the flowers, or the petals or each petal. How you determine that, or decide that I think is a pretty difficult question. It seems like in this one, you just leave it out, you mask them out. It's going to have a uniform distribution number of objects, that's the way you get around that problem in a practical sense.

**Katja Schwarz:**
Exactly. I think there's a fair chance that if you incorporate more supervision, like segmentations or depth as well, that you could again, boost this model.

**Kanjun Qiu:**
You published on with Yiyi Liao, and then the next paper was using radiance fields. How did you go from this, working with point clouds to moving to radiance fields? And can you tell us a little bit about the next paper?

**Katja Schwarz:**
Well, what we noticed during the CVPR project was that it's actually really hard to scale this approach to photo realism. And one reason for this in our opinion, was the 3D representation that we chose. Why these primitives are great, because they're simple. We found that maybe to scale it up to high photo realism, and also to ensure a more consistent behavior. Because sometimes in the CVPR project we saw that if we rotate the primitive, that the object flips that direction.

**Katja Schwarz:**
You had that 180 degree flip. And we thought maybe there is a better way to encode a 3D object while it still scales, while in it's compositional, so you can extend it. This is where radiance fields became really interesting. But the first thing that we thought is, probably it's a good next step to simplify the problem a little bit. And go one step easier, and go to single objects before we tackle even more complex scenes, get a really good approach on single objects first, and make it work there.

**Katja Schwarz:**
This is why we changed the whole problem setting from scene spec to single objects, to get something that's really satisfying in that area. The neural radiance fields paper came out and we were like, "Oh, that sounds like a great representation for our purpose." It's a continuous function. It scales fairly well. It's good in terms of memories, seem to be an ideal fit. And we thought, "Let's use this and let's play around a bit and try." And this is how we started working on the second project.

**Josh Albrecht:**
The second paper is called GRAF: Generative Radiance Fields for 3D-Aware Image Synthesis. Can you give a very brief overview of what the general approach is, how it works, et cetera?

**Katja Schwarz:**
The general idea in graph is that we represent 3D objects as neural radiance fields, or we parametrized them as a conditional radiance field. Then we use a physically inspired rendering approach to create images from these 3D representations. The main benefit of our method compared to existing works in this area is that we can actually scale to higher resolution, because we do use this continuous representation that scales beneficially with increasing image resolution.

**Josh Albrecht:**
The robustness of the 3D point clouds I thought was particularly interesting in the way it worked on datasets. You wouldn't expect to have a whole bunch of interesting 3D information that faces datasets, HQ, and things like that. Do you think that you guys succeeded in what you set out to do? Or were there things that were left that you're like, "Oh, if only we could have done X."

**Katja Schwarz:**
There's a trade-off between how flexible you make the model, and how consistent we get really good results. But it's still not this photo realism where I really would love it to be in the best case. I think we could still get better outputs in terms of how realistic it is. The main limitation here was how flexible you make your model. In our case, we really wanted to have it 3D-consistent.

**Katja Schwarz:**
For us, it was really important that if you change the perspective that you don't get this flip of identity, but if you learn the rendering process instead of using this physically inspired approach, you tend to get higher quality in your visits because you can actually learn these fine details. On the other hand, your rendering can learn whatever it wants, and it's hard to restrict it. You can put an extra constraint on it. That also feels a bit cumbersome. It's a trade off.

**Katja Schwarz:**
And especially if you don't have the camera information, you don't have exactly the right post distribution, you will always have a little bit of error in it. It still prevents the images from looking perfectly. We chose a very simple camera model just on the hemisphere, the more or less fixed radius. If you would make this more advanced, if you could learn this, maybe you could get even better results.

**Kanjun Qiu:**
In the realm of making image generation controllable, what do you think are the biggest bottlenecks or what holds us back?

**Katja Schwarz:**
One of the biggest bottlenecks, we already touched it a bit in our conversation is that you need to get a stable GAN, and you need to make training work. Currently, there's a lot of intuition that needs to go in there, and it's really tricky to get these models stable. That's one of the bottlenecks that GANs are currently still very challenging to train, and very difficult to work with. And it's usually not the case that you apply a method and it just works out of the box.

**Katja Schwarz:**
You always need to spend a lot of time to really get it to work on this data. This is one part. And then the other part to really make things 3D-controllable is the lack of 3D supervision. Usually for real-world scenes, you don't have a 3D model for everything that you can use to supervise, and you don't have a 3D model of the exact object that you want to model.

**Katja Schwarz:**
Our approach that you can learn this from images is already a step in a good direction, but the advances in neural rendering and differential rendering, that's now possible, which is great. But you still need to find a good way to incorporate at least a depth map or something that gives you a bit more information to really scale up to more complex scenes. It's the question, how much supervision can we realistically get? And how can we smartly incorporate it into the model?

**Kanjun Qiu:**
Do you think that as a field will ever move past GAN training, something better for generative neural rendering work than GANs?

**Katja Schwarz:**
It's a philosophical question. I feel if you're more VAE person or more a GAN person. But currently, these are the two main approaches. All the other models, at least in terms of image fidelity currently, they're not on par. I'm more like a GAN person, but obviously I really think in the VAE setting, it's also very intriguing that you have this encoder part, and that you can do inference.

**Katja Schwarz:**
And these are things that are missing in GAN training, and sometimes it's at its more stable, because you can actually reconstruct the image. In our last project, we were actually thinking about using a VAE approach, just because of these nice stability properties. Then we decided against it because it meant that we would need to use posed images. Because if you want to reconstruct it, you need to know which pose it was taken from. And that's an advantage then again for GANs where you don't need to reconstruct exactly the same image.

**Kanjun Qiu:**
What are your concerns or ethical concerns related to the research fields? Do you have ethical concerns? And what can you think about?

**Katja Schwarz:**
It's always tricky if you work with generative models, because if you have a super good generative model, you can do amazing things with it. But of course you can also do misleading things with it, and you can generate content, and maybe create scenarios that are not real. If we make the step from 2D to 3D work, which I helped because I find it super interesting, it will greatly improve the feeling of realness in these VR applications or in the generated content.

**Katja Schwarz:**
But at first sight, this is not necessarily a bad thing. That's exactly what we want. But you need to be careful, and we should really pay attention that we also have methods that can detect this generated content. Also what I feel is important, if we really think we're able to generate realistic 3D environments. It's very important that these technologies they should rather assist our everyday life.

**Katja Schwarz:**
They should not replace it. It should maybe make it super nice. If we talk over Zoom and you directly see the people. It's like 3D and feels more real. But it should not lead to people being more caught in the virtual world even more than they're now. And have people spend even more time on the virtual profiles, and that, that would not be the right direction to go. I think just try and be aware of these directions, and always ask which direction do we want to choose.

**Kanjun Qiu:**
When I think about more general intelligence or all of these machine capabilities, I always think about, we have an option to create a more humane world or a less humane world. And the dichotomy you described which is, if we're faking a lot of content, there's less humane in some important way. Whereas if we're using it to enable ourselves and a lot of humans to be more creative, then that's more humane in some important way.

**Kanjun Qiu:**
I think you're right about these concerns and how we should think about it as a field. You got from physics to here, whose work has impacted you the most? What papers have you spent the most time reading or understanding?

**Katja Schwarz:**
The transition from physics to here was not so much based on specific paper or specific works from one person. One of the first papers I read when I started doing my PhD, it's called, Which Training Methods for GANs to Actually Converge? It's from one of our former group members. The reason why this paper impacted me so much is just because I really loved the whole method or the whole approach that he takes towards building a theory or building a hypothesis, and verifying this hypothesis.

**Katja Schwarz:**
Though at this time, GANs was still even harder to train than now. And they start from a very simple setting. They think of what's the easiest problem that a GAN can solve, and they come up with a very simple distribution. Basically, it's just one number and it's a very nice approach to break it down to the car, and really see what are the problems there?

**Katja Schwarz:**
The reason why this impacted me the most is because I really like this way of approaching a problem, to really think about what is the core problem that I want to investigate, and then you formulate your hypothesis, and you try to narrow it down to just an experiment where you really can just test the single thing. In this paper then, they explain it in a very simple example, but then they scale up. And then they show that you can greatly stabilize GAN training actually, if you use their method. And I really thought that was a great approach.

**Kanjun Qiu:**
Can you explain a little bit, what is the core hypothesis that they narrowed down to, and then how did they scale it up?

**Katja Schwarz:**
They show that existing gun training methods, they don't even converge. If you give them a very simple setting, the generator only needs to predict one number because it's like in physics, when you want to optimize for something, but then you overshoot. Like a pendulum and swing, but they swing by the minimum and they actually don't converge.

**Katja Schwarz:**
The main idea is then to introduce something like a friction term. You put some friction in the optimization on the gradients basically, and then you can actually converge to a good minimum. That's the core idea of the paper

**Kanjun Qiu:**
Did you use that when you were training your GANs?

**Katja Schwarz:**
Yeah, I always use it. It makes a huge difference. And actually I think all of the state-of-the-art methods now use this, regularize it.

**Kanjun Qiu:**
And you mentioned you really like this idea, this methodology of getting to really a core hypothesis and starting very simple. Did you apply that to any of your own work?

**Katja Schwarz:**
I usually try to go this way. And then I talked to my professor and he tells me that's not simple enough. And then I try to simplify it further. Over the course of the last one and a half years of my PhD, I always came to the point where I thought, "I'm still thinking way to complicate it. I need to make it simpler." For example, for the Generative Radiance Fields project, we also started with a super simple setting. And what I usually like to do for GANs is to start from regression.

**Katja Schwarz:**
You first try to reconstruct only a single object, and then you start from there, because that's fairly stable. And then you condition your model on random variable or on the latent code. But maybe you first condition it even on one encoding or a class, and then you try and regress multiple objects, and reconstruct them first. If you've got it working on reconstruction, and then you can start to introduce more randomness. And by this, you increased the difficulty of the task gradually.

**Katja Schwarz:**
For me, that always worked best because usually if you just apply a gun and you just train on it, it never works. It just crashes. It's exactly what we do in our research. We always try to break it down, and make it very simple.

**Josh Albrecht:**
Can you describe the extremely simple thing that you started with for GRAF?

**Katja Schwarz:**
We took a very simple object on a white background and we just really tried to reconstruct it. Our method is based on a method that's actually optimized for not the view synthesis, which is called neural radiance fields. And we augmented a bit, so it can work in a GAN setting. This work works where users post images. We try to take the post images away, and start it from very simple reconstruction. And then we try the same object, but multiple views.

**Katja Schwarz:**
We introduced a GAN loss at one point, but we always in the beginning also use camera poses, use reconstruction. I remember that we also did a trade off. Sometimes we were helping the model by still using a reconstruction loss on some images, and gradually increased how many images we train with the GAN loss, and how many images we trained with the reconstruction loss. And I wrote down this part.

**Josh Albrecht:**
That's not part of the final paper. That was just something you were doing as you were experimenting with it.

**Katja Schwarz:**
Yes, exactly. That was basically just to get it to work in a very simple setting. And then as soon as you found the balance between the generator and the discriminator, then you start scaling it up.

**Josh Albrecht:**
That's really interesting and probably-

**Kanjun Qiu:**
That's actually really interesting part.

**Josh Albrecht:**
... very helpful for other people who might be doing this for the first time, for example. I don't think I would necessarily have thought to do that originally. Are there any other things that didn't fit in the paper, or tips, or tricks, or things like that?

**Katja Schwarz:**
What made a huge difference was this position at encoding that we use, but that's also part of the neural radiance fields paper. We knew that, that would help a lot about this position that encoding our results look very overly smooth. For GANs it's also always true that you just need to do a lot of ablations to really see which kind of normalization did you want to use? You want to use batch norm or instance norm.

**Katja Schwarz:**
And from the previous project and the GRAF project, it's hard to say which one to use because for both projects, we found different things to work well. Usually for tricks, it's just do ablations. Do a lot of them, try to figure out which setting in this case works the best. Unfortunately, it still requires a lot of intuition. And usually a person who is already quite familiar with GANs can tell you a bit about it. Otherwise it's very hard to really get familiar with it.

**Josh Albrecht:**
Do you feel like you've built up that intuition over the past year and a half?

**Katja Schwarz:**
Yeah, I hope so. But I feel I did. In the beginning, I remember that we used a special type of normalization for the CVPR project, before our model was always unstable. And then we normalized our weights, and suddenly it was super stable. That was like pure magic. I didn't know what was going on. But because this happened, you pay more attention to these things, and then you really get to build an intuition of, why is this working or why is it not working? How big should my discriminator be?

**Kanjun Qiu:**
I wanted to go back to what you were saying earlier about how the focus was. You wanted to make generative modeling controllable. Your interest is in making visual scenes understandable because there's a lot in a visual scene. Why did you pick this question of generating things in a controllable way? And did you consider other questions or anything else toward this idea of visual understanding?

**Katja Schwarz:**
If you can generate something or if you can create something yourself like a prototype, it's nice because you can see as a program of what your model learned from the data. And on the other hand, if you reconstruct, it's way harder to see if there's a true understanding, or if it's just rapid juicing things. I guess why I favor this GAN approach because I feel that there's a lot of potential also for robustness. It's closer to this understanding. We humans can also think of different versions.

**Katja Schwarz:**
If we think of an object, we can build an abstract version of it. We have these prototypes in our head. This is also very closely linked to an understanding, and to transferring skills or transferring the concepts.

**Kanjun Qiu:**
There's a really interesting TED Talk by this guy named Anil Seth. He's a neuroscientist, called it, Your Brain Hallucinates Your Reality. And it talks about the mind's eye, and how humans in our mind seem to make predictions about what we're perceiving. And the predictions are based on what we understand of what's going on right now. And he shows a bunch of really interesting examples.

**Kanjun Qiu:**
It feels related to this idea that, yes, humans are generating something. We're not just taking what's in the world and reconstructing it in our mind. We're hallucinating something new based on some underlying model.

**Katja Schwarz:**
Yeah, exactly. And you can transfer this knowledge that you've gathered, so you can apply it to new things. Reason why we can do this is because we have this abstract kind of thinking. I'm not sure if you can get there just by reconstruction. That seems more like reproducing knowledge. But for me, a vital part is how to obstruct it.

**Josh Albrecht:**
There might be a counter argument to this for people understanding the scenes. For example, if I imagine the outside of this house, my imagination is pretty blurry. I guess I can fill in the details, but these GANs are way better at making face images than I am. They have such good detail. They're amazing. Even if I open Photoshop or something, it take me days to make something like this. How much of the expressive power of the network is going to get in all of these details versus the understanding part? And is there a balance between those two?

**Katja Schwarz:**
I think a lot of compute goes into the details and goes into very tiny things. That's probably where you spent the most time in training. If you look at the cars over training, what the model learns first are these rough structures. If you would train a GAN in the setting, what it would probably learn first, it's the rough shape of the house. At least for our project, the model was really fast at getting a rough shape of a car, or a rough shape of a face, or something. That happens super fast.

**Katja Schwarz:**
But then you spend a long time to really get these fine details. If we talk about understanding, maybe that's not even necessary. Maybe it would already be enough if the model can get rough shapes. But I feel it's also a bit related to what do we need to learn from scratch, and where can we use already known rough shapes of houses like rough 3D shapes. Maybe we can insert this knowledge somehow, and we can speed up this process even more, so that even the first couple of iterations, it doesn't need to spend on learning all of this.

**Josh Albrecht:**
As you said, most of the GAN training is like, first it gets a rough shape, and then after a really long time does all the details, and we finally get good images mentally. Is there some way to invert this where you say, "We actually don't really care about the fine details. Instead what we want to do is use our training time, use our capacity to get tons of diversity, to understand lots of different object, class types and scene types. Not very well. They'll be bad reconstructions. We'll have a lot more richness in what we can express and think about."

**Josh Albrecht:**
I don't really know how to put that into an actual experiment or actual network. But I was wondering if you had any thoughts on that.

**Katja Schwarz:**
I'm not aware of any works that do this currently. One nice way to get something like this is if you penalize your discriminator. A discriminator gives you your training signal. If you make it for example, blind to this fine detail somehow, you can probably prevent the network from learning it because it doesn't need to learn it anymore.

**Katja Schwarz:**
That might be a good idea, but then how to really increase diversity. I think that's always a very good question in GAN training, because they have this tendency to get to mode collapse. If you think for example of MNIST digits, a classical example would be, it can only generate ones and twos and everything else it cannot generate any more.

**Josh Albrecht:**
You have a generative that doesn't have expressiveness to do all the classes you have, but even MNIST example is a really great one. Ones and two is great. There's only eight in ten numbers. In the real world, there's so much more diversity.

**Kanjun Qiu:**
Early, you were saying you're in the GANs camp, and there are other people in the VAE camp. The people in the VAE camp, what is their argument for why they're in the VAE camp and not the GAN camp?

**Katja Schwarz:**
The main counter argument is that you can do inference. You do have an encoder, and with this, you can do a lot of cool things. For example, if you want to control an object and you would have an encoder, it would really nice because you could actually take a scene, encode it, and then modify exactly the objects in the scenes. And this is something that our model currently cannot do.

**Katja Schwarz:**
With GANs you can always go the other way around. You can take the image, and then go backwards, and such for the closest latent code to the scene. But it takes a lot of effort, and I think in that sense VAE is more and more elegant.

**Kanjun Qiu:**
And what is your kind of argument to that argument?

**Katja Schwarz:**
The image quality is higher if you use a GAN. There's highly engineered VAE approaches that are almost on par with it. You can get up to that accuracy, but it's not your normal out-of-the-shelf VAE that can produce these sharp results.

**Josh Albrecht:**
I think those VAEs do have some trade offs in terms of, at least the ones that I was looking at NeurIPS. It seems they have to train for a really long time, or they seem impractical to train. It wasn't directly how they compared to GANs in terms of training time, and model size, and things like that, but they were on par. And GAN is also taking a really long time to train, and a lot of competition resources or if it's much more efficient to train together. I wasn't really sure.

**Katja Schwarz:**
To be fair I think, if you look at the state-of-the-art GANs like StacKGAN tool, they also take ages to train. This is why for us it's more like which approach has performed better in the mid range. If you're not looking at top state-of-the-art approaches, but you're trying to make it train in a reasonable time, StacKGAN seem to be the better way to get sharper results there.

**Josh Albrecht:**
How long did your models, of both the first and the second project, how long did the models take to train as you were iterating on the experiments and also for the final one as well?

**Katja Schwarz:**
During iteration, it's usually over one night. You started in the evening and the next morning you know if it's doing the right thing. And usually you know after a couple of iterations, maybe after one or two hours. Even, you can tell if it does something reasonable or not. For the debugging cycles that we had, they were rather short. And then for the final versions in the papers, we'd train three or four days maybe, maybe if we let it run for very long, we train for a week, but only on a single GPU, we didn't use excessive class computing.

**Josh Albrecht:**
They're very achievable. Someone could do this at home, basically.

**Katja Schwarz:**
Yeah. We have a very simple toy data set with cars. You can train this in one day on your GPU, I would say.

**Josh Albrecht:**
And so much more in that fold. Oh yeah, I need a cluster with more memory than the entire university has.

**Katja Schwarz:**
You still need a GPU. But I'm also a big fan of people who write these short Colab notebooks, where you can use their model and it works, and even a simpler setting. And you can really just run it and just stay with a code.

**Josh Albrecht:**
You open sourced at least one of them or was it both of them, or just one of them?

**Katja Schwarz:**
Oh, both papers are open source, yeah.

**Josh Albrecht:**
Extremely great. Did you guys also make notebooks for them?

**Katja Schwarz:**
Unfortunately we haven't yet.

**Josh Albrecht:**
Maybe somebody else listening can go make it for you then.

**Katja Schwarz:**
That'd be great. We do have scripts basically that you can just run in Python, that just generate images and where you can change the camera pose to change the appearance. We do have these scripts included. It's just not in a ready-to-run notebook, but it will do everything automatically. It downloads the weights and everything.

**Kanjun Qiu:**
I'm thinking about what it means to really understand the scene earlier. And you were saying the benefit of the GAN approach is that it results in sharper images over the VAE approach. And Josh was saying, "When I imagine the outside of the building, it's not very sharp. It's very blurry in my head." And so I guess I was thinking toward the goal of understanding of scene. Does the sharpness really matter, or do you think the VAE has a potentially equivalent ability to get to understanding?

**Katja Schwarz:**
Well, there's not really a benefit why you should only use a GAN for this type of task. Maybe it's even more beneficial in that sense to use a VAE because you can use an encoder pod, and then you can encode scenes as well. This is just one aspect. For example, if you think of augmented reality or virtual reality, you also really want these sharp details.

**Katja Schwarz:**
Just find a standing, yeah. If you want to augment data, which is also one of the big hopes for application, maybe you want to create a data set with rare events, for example, in autonomous driving, maybe you don't want to record some scenarios. And then it would be nice if you could generate them without having them in real life. In this case, you actually really rely on these details because otherwise you might get domain gap. And then your model, when you train it on this data, it will actually just spot the generated images and it will treat them differently.

**Josh Albrecht:**
I was just talking with a friend about the idea of using GANs for generating training data for other models. What do you think about that idea? How far off is that? Will it ever happen? What are some of the trade-offs?

**Katja Schwarz:**
GANs can be a really good opportunity to close the gap between toy data and real data. Currently, there's a huge domain gap. My hope would be that a GAN can be used intermediate step, so you can close this domain gap. In most cases, we're not there yet because our generated images are still also having this gap to real data, or they're not controllable enough yet. And you need to make them more controllable to generate the data that you want.

**Josh Albrecht:**
Well, it seems like we're making good steps in those directions, at least.

**Kanjun Qiu:**
Do you have any intuitions about the important directions you want to investigate next or important open questions that you're interested in right now?

**Katja Schwarz:**
Yeah. I'm currently really interested in how to make GANs easier to train. Because that's one of the main things that make the advances in our field so time-consuming. But I also think the supervision part would be really interesting to see how much do we need to learn from scratch because we train from images, but we learn everything from these images, and somewhat more supervision to incorporate depth as we discussed before. I think these would also be really interesting questions. I would also like to work on this too.

**Kanjun Qiu:**
Do you have controversial opinions or a neutral opinion you think other people would not agree with?

**Katja Schwarz:**
Well-engineered models are better than brute-force high compute models. Currently the trend is to increase model size, increase datasets. Recently I saw a paper about image transformers, where they say that image net is a very small data set to train on, and they use these huge data sets. I find this super interesting and very fascinating that they can make this work.

**Katja Schwarz:**
I still feel that it's nice to have a well-engineered model, and try to make it efficient in terms of compute. But maybe that will change over time.

**Josh Albrecht:**
Even if you had a really amazing, huge model, there'll be a pressure to make it smaller and cheaper. There's a reason that the human brain, I think uses 35 Watts or so?

**Katja Schwarz:**
[inaudible 00:39:19] or something.

**Josh Albrecht:**
Yeah, something really small. Way less than a GPU, to do everything it does. I think there's going to be pressure to make these things smaller, and I don't think the need for a smaller, more efficient, better architecture is going to go away.

**Kanjun Qiu:**
You made a good point the other day, Josh, which said, "You could scale up anything, and it will perform better." But it's more valuable from a research perspective often to find the right thing that you can eventually scale up. And to figure out that right thing is very difficult. It requires a lot of thinking about what might the model architecture look like, and can we innovate there? Do you have any other controversial opinions aside from the scale one?

**Katja Schwarz:**
One more is to represent 3D objects in terms of continuous functions. Especially in the last half year, there was another boost of this form of representation, but currently many people still work using mashes or voxels. It's probably also biased. In my group, we do a lot of work on this continuous functions, but I really like these types of representations.

**Katja Schwarz:**
I find it just very elegant to encode your representation or your 3D object as a function that you can query wherever you want, and you can choose the density which you query, and it gets rid of this discretization. It's maybe not so much controversial, but rather not the mainstream yet.

**Kanjun Qiu:**
Controversial just means, but not the mainstream.

**Josh Albrecht:**
I strongly agree with this whole line of work. It's super interesting. And actually one of my questions was going to be, how do you feel about this field and getting so much hotter? And I feel like there's so many people swarming in, [inaudible 00:40:47] from NeurIP and related thing.

**Katja Schwarz:**
We get a lot of attention, which is great, but you also need to redefine these things, and you need to make sure that not suddenly everything becomes a big blur and people just use the terminology. Many people use implicit function, the term itself to describe a continuous function. But implicitly means really that you define your object with a decision boundary of a classifier. And so it's implicitly-defined.

**Katja Schwarz:**
Usually our neural networks, they are continuous functions, and what makes them continuous in the sense that it's usually used as the input space. This input grid that is continuous, and now I can query it at whatever point I want. It's not even the function itself where it's a special, that it's a continuous function. It's rather the input that you give it that's continuous and you can query it in between.

**Josh Albrecht:**
Do you think that everyone shares those definitions or

**Katja Schwarz:**
I don't know. The papers I read currently, I'm not sure if there's a clear line of definitions that everybody agrees on. Internally, we do agree on these definitions, and it also happened to me in the beginning. I was like, "Can I call it implicit function or not?" And then it's just very tempting. But I think there is not a strict definition that you can look up for. It exactly tells you this. This is more our understanding here in the group, how we define it.

**Kanjun Qiu:**
You mentioned using continuous functions as representations for three objects is an interesting concept that you felt was underappreciated before. Are there other things that you feel like deserve to be more widely known or they're underappreciated?

**Katja Schwarz:**
It's maybe not so much a different representation method. What I find under appreciated are guides to how to train your models. There's a great blog post by Andre Karpathy, where he tells you a step-by-step recipe on how to train a network. Just for our course, I recently had to look at it again. I really like this post because it tells you that you should start simple, and that you should take a look at your data.

**Katja Schwarz:**
And this is something that's a bit overlooked because it's become so simple. You can just use PyTorch and you can put the models, and then you train, and you can write a nice code in, I don't know, 100 lines. But like all the subtleties, they get lost there. But this is why I really liked this recipe. Also what it tells you is that if you're lucky, your network will crash, and you will get an error and you will mess up.

**Katja Schwarz:**
And that's the good case, because in the bad case, you will not know. And maybe you discover it after you submitted it somewhere, and then you notice, "Oh, this part is not doing what I thought it would do." And then you change it, and everything changes. It happened to me in our first project, luckily in an early stage. But I didn't notice that my model was actually not doing what I thought it would be doing.

**Katja Schwarz:**
And it cannot be emphasized enough that people should really be careful when they train these things and not just, "Train, and it works, and great if I don't get an error. That's perfect. Now it works."

**Josh Albrecht:**
What was the thing that was overlooked in the last project?

**Katja Schwarz:**
We used the final sigmoid function. We accidentally applied it once in the last function. And we also applied it in the model.

**Josh Albrecht:**
[inaudible 00:43:47].

**Katja Schwarz:**
... and that greatly harmed our gradients and made training a lot worse. We had another buck at some point for the normalization where we had a reshape era, where we thought it was channels by batch size or something, but it was the other way round. And we didn't notice because we reshaped. And in the blog posts, he also gives you a tip on how to do this, that you can actually track the gradients, and see if you get the right gradient. We should have probably done this, and then it wouldn't have happened.

**Josh Albrecht:**
Those are great to share also, and to help other people realize the importance of doing this, having time. Yeah, read that blog post.

**Katja Schwarz:**
The first, I don't know, five-minute-read or 10-minute-read is really just about the data set. And I feel that's also justified, that you do need to spend a lot of time on your data. And for the GAN training, we noticed that, for example, we make the assumption that our objects are centered in the scene. It's really important that this is also true in your data, and that you actually prepare your data right.

**Katja Schwarz:**
Especially in the beginning when you try to get it to work, if you're not careful enough there, I think that can also cost a lot of time if you afterwards find out, "Oh yeah, sure. It couldn't have worked."

**Kanjun Qiu:**
Were there any very recent papers that really stood out to you?

**Katja Schwarz:**
There's a couple of papers, but one that I have in mind where they train a fully connected neural network to generate images, which are almost On par with StacKGAN FID wise. It's called image generators with conditionally independent pixel synthesis. It was surprising so that it works because usually we thought with these big images convolutions are these things to go.

**Katja Schwarz:**
It was just very surprising that just by conditioning on a common latent code. Then actually using fully connected network without any spatial correlations, you can still generate quite coherent looking images, and they still make sense. The image quality is really, really good, but they don't use any convolutions.

**Kanjun Qiu:**
That's so interesting. What are the advantages of using a fully connected network and conditioning on the common latent code over using something publishable?

**Katja Schwarz:**
The main advantage is that you can parallelize the computation if you use an MLP, because everything is independent aside from the shared latent code. At least from what I got, this is the main advantage of these methods.

**Kanjun Qiu:**
You mentioned there were a couple of papers. What else?

**Katja Schwarz:**
There's one that is called continuous image generation, something like this. And it's also a similar approach. They found that the other approach for them it didn't work as well. They take a different turn and I think they need to share a little bit of information between the last, but I'm not entirely sure anymore. They all generated images from a shared latent code, but they all generated images using only fully connected layers. This is just a very new approach.

**Katja Schwarz:**
It's somewhat also what we did with the Generative Radiance Field. We also used a fully connected network and we generated images. In terms of the image fidelity in the photo realism, these methods are a lot better. They're not really controllable or anything. They're more like the conventional GAN. I find it super impressive. They got this to work and that they can get especially coherent images from this.

**Katja Schwarz:**
Maybe the basis for these works was this position of encoding that we also talked about for a little bit. Now you can encode your coordinate grid that gave rise to a lot of more interest into these fully connected networks, because now you can get these really sharp images from cardinal-based representations. There's another paper that's called [inaudible 00:47:00] Features. I'm not sure about the whole title. And then there's another one called Sinusoidal Activation Functions. These two works, they came out fairly at the same time and they are touching the same problem, and I found them really interesting to read.

**Josh Albrecht:**
One of the main authors was [inaudible 00:47:18]. And I think we're going to have him on the podcast in another week or two, probably so.

**Katja Schwarz:**
Oh, nice. Yeah, I guess then he will also tell you a lot about the continuous functions or the implicit functions.

**Kanjun Qiu:**
You and Josh had very similar tastes in these papers. Are there any areas that you're really excited to see develop over the next few years?

**Katja Schwarz:**
One area that I would love to see develop is how close we can get to generating realistic 3D scenarios and scenes, and how this whole research area develops. Also linked to this, one of the groups at the institute that I work, they also do a lot with human modeling. I would also love to see how far you can push it in that area. Ultimately, maybe you would just quickly take a selfie or something, and get your 3D avatar targeted to you. And then maybe, I don't know, you can use generative model to change your house style or something like this.

**Katja Schwarz:**
This whole idea of remodeling our world more or less in 3D, how far can we push it in the next years? Another thing is in general the robustness of the models. We also work a lot on autonomous driving. The models are currently not robust enough so that they can really be deployed, or go out and can just be used.

**Katja Schwarz:**
It would be really nice to have even more theory behind neural networks, if we can make any progress. I know that there's a lot of works already that touch on this area, but it still feels that we do rely a lot on intuition and not only in generative models, but in all areas. Very often written a paper like we think that this and this is the explanation, but it's very rare that you actually see a proof that this is the explanation.

**Katja Schwarz:**
That's a very important point that we can advance in this area to get some more guarantees or to make models more robust, at least to know when they fail. That's very important because otherwise I don't see how we can use these models in our everyday lives, and really rely on them at some point.

**Kanjun Qiu:**
What are the highest leverage areas that might increase robustness or where you'd like to see more work in increasing robustness?

**Katja Schwarz:**
There's a fair amount in adversarial examples. What I personally would like to see is to go back more into this generative setting. I know that there are some works that also train robust models based on generative models. And this idea that if you learn this prototype, then you have a rough idea, and it's harder to get confused if you have this rough prototype. I think it's the fatty reason, it would be very interesting to see if it's really true, that this understanding that I think GANs can have, or can learn, which makes them a bit better, but more robust.

**Katja Schwarz:**
If we can actually use this to really train robust models or determining confidence. If you would imagine you have a GAN and it is very good at giving you the same data distribution, you could use the GAN to visualize what your model has learned.

**Josh Albrecht:**
Me the only last question that I have is a two-part thing. One, is there anything that you feel stuck on or like, "Oh, I'm not really sure how to do this." Similarly, is there anything you would like people to reach out with? Are you looking for any collaboratives in a particular thing, or people to send you papers about problem X? Is there anything you want from the community and people who are listening?

**Katja Schwarz:**
If somebody knows any related work to generative models and increasing robustness, that would be great. And if people can send papers I haven't had a close look, I just know some works for like one or two years ago, and I was very excited about it, but then I lost checks.

**Kanjun Qiu:**
This is really lovely.

**Josh Albrecht:**
This is it.

**Kanjun Qiu:**
Thank you so much.

**Katja Schwarz:**
Thanks.

**Kanjun Qiu:**
Thank you for listening to Generally Intelligent. We love feedback and questions. Please feel free to ping us on Twitter at @kanjun and @joshalbrecht or email us with any ideas or corrections. If you enjoyed this podcast, please share it with fellow researchers, read it on iTunes and follow us on Spotify or your favorite podcast app. Thanks very much. And we'll see you next time.


