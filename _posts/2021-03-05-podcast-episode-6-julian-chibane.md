---
layout: post
title:  "Generally Intelligent #6: Julian Chibane, MPI-INF, on 3D reconstruction using implicit functions"
date:   2021-03-05 09:00:00 -0700
category: machine-learning
tags: podcast 

author: 
- <a href="https://twitter.com/kanjun">Kanjun Qiu </a>
- <a href="http://joshalbrecht.com/">Josh Albrecht</a> (<a href="mailto:joshalbrecht@gmail.com">email</a>)

---

**[RSS](https://anchor.fm/s/42cab330/podcast/rss)** · **[Spotify](https://open.spotify.com/show/1hikWa5LWDQJwXtz5LoeVn)** · **[Apple Podcasts](https://podcasts.apple.com/us/podcast/generally-intelligent/id1544921720)** · **[Pocket Casts](https://pca.st/ewh266dr)** 

<iframe id="podcast-embed" src="https://anchor.fm/untitled-ai/episodes/Episode-06-Julian-Chibane--MPI-INF--on-3D-reconstruction-using-implicit-functions-ermvhn" width="100%" frameborder="0" scrolling="no"></iframe>

Our next guest, [Julian Chibane](http://virtualhumans.mpi-inf.mpg.de/people/Chibane.html), is a PhD student at the Real Virtual Humans group at the Max Planck Institute for Informatics in Germany.

His recent work centers around intrinsic functions for 3D reconstruction, and his most recent paper at NeurIPS is [Neural Unsigned Distance Fields for Implicit Function Learning](http://virtualhumans.mpi-inf.mpg.de/ndf/). He also introduced Implicit Feature Networks (IF-Nets) in [Implicit Functions in Feature Space for 3D Shape Reconstruction and Completion](https://openaccess.thecvf.com/content_CVPR_2020/papers/Chibane_Implicit_Functions_in_Feature_Space_for_3D_Shape_Reconstruction_and_CVPR_2020_paper.pdf). Julian is open to collaborators interested in similar work, so feel free to reach out! 

<div class="parent">
<div class="column" style="flex: 1.71">
{% include image.html 
url="/assets/img/podcast/julian-chibane-ndf-teaser.png" 
alt="Results of Neural Unsigned Distance Fields (NDF)" 
caption="Neural Unsigned Distance Fields (NDF) can represent and reconstruct complex open surfaces. Given a sparse test point cloud (left), it generates a detailed, completed scene (right)."
class="large-image"
%}
</div>
<div class="column">
{% include image.html 
url="/assets/img/podcast/julian-chibane-if-nets.png" 
alt="Results of IF-Nets" 
caption="IF-Nets can reconstruct point clouds where a part is is occluded, e.g. the human's back (left), with continuous outputs (right)."
class="med-image"
%}
</div>
</div>

Highlights from our conversation:

🖼 How, surprisingly, the IF-Net architecture learned reasonable representations of humans & objects without priors

🔢 A simple observation that led to Neural Unsigned Distance Fields, which handle 3D scenes without a clear inside vs. outside (most scenes!)

📚 Navigating open questions in 3D representation, and the importance of focusing on what's working


### Some quotes we loved
> **[08:34] What surprised him while working on IF-Nets:**
How strong neural networks can be! We started with simpler tasks for the paper, but then we started to do some crazy stuff, like just completing the human body where an arm is missing and things like that. The network really does something very reasonable, really learns how a human should look. That was surprising for me actually, that these convolutional layers really do learn something pretty reasonable.

> **[13:25] Why IF-Nets generated better reconstructions:** 
One very important reason is that we include local information of the inputs, but also encode more global information. If you want to complete the backside of a human, you really need to know where you are relative to the input point cloud, which is maybe only of the front [of the human]. Then you need something very global. The main contribution of the paper is to show how to combine local as well as global information from the input.

> **[28:42] Why implicit functions have had such an impact:**
Representing 3D scenes is not so easy as representing a 2D image. For 2D images we know how to represent them: we use grids and for each point in the grid, we have the RGB value stored and that's it. We all agree that this is a good representation for an image, or at least it's a very common representation for an image. 
But it's different for representing 3D scenes, especially for learning. Mesh is a very dominant representation of 3D surfaces, but it's not so easy to learn with those when you're applying a neural network.
That was why these implicit [function] papers had such an impact, because this representation wasn't so clear.

> **[44:42] Research as a discovery process:**
Having people who believe in you telling you that what you're doing is still worthy [is important]. After coming up with these IF-Nets, but having had a different goal, it wasn't so clear for me after working so much that this is still something useful. But then you have to be reminded again, that if you change the setting, this is really useful for other people or for a different setting. That was also something I'd learn.
Many people forget that other stuff is really working well, and instead of pushing what's working, they try to engineer what's not working.  Sometimes shifting the focus is very helpful.
In research, if you already know that everything is working beforehand, then it's not really research. You have to be open for this discovery process, which is not always as easy as it sounds.

> **[45:00] On simplicity:**
I really tend to like small steps in research better than having highly engineered big architectures that solve one task very well, where it's not really interpretable where this is coming from. 
I think that's why NeRF is so popular, because it has a very simple representation. It uses stuff that's absolutely clear to readers, for example a fully connected network. Also, including volumetric rendering, which is known—they take key things that are known, but do something very important and helpful with it. It's very clear why it's working and why it's not working, instead of sometimes you have papers solving some task but they have four different networks in there, that do not have any real names, they're just doing something not interpretable.

*Below is the full transcript. As always, please [feel free to reach out](https://twitter.com/kanjun) with feedback, ideas, and questions!*

<!--more-->

<br>


**Kanjun Qiu:**
Julian is a PhD student at the Real Virtual Humans group at the Max Planck Institute for Informatics in Germany. His recent work centers around intrinsic functions for 3D reconstruction and his most recent paper at NeuroCS is called Neural Unsigned Distance Fields for Implicit Function Learning.

**Kanjun Qiu:**
Tell us about how did you get to where you are and develop your initial research interests.

**Julian Chibane:**
Yeah. Already as a child I was very fascinated by image processing, for example, 3D rendering. That was really something I loved and played around with in a really early age, and video editing for example. I did this with computers. My mother was a computer teacher and in the university, I had courses on statistics, computer vision, and 3D point cloud processing. I really felt that this is something really cool and was really drawn into this.

**Kanjun Qiu:**
What did you find cool about it?

**Julian Chibane:**
In 3D point cloud processing we learn from images, we can reconstruct the world in 3D and it was pretty amazing for me to go from a 2D projection of the world into something that's 3D interpretable that you can render from different viewpoints and representation of the world is much more interactive than just an image. You can look at an image but that's it; you cannot really move the viewpoint or stuff like that. With the 3D representation, you can do just so much more and you might even be able to let an agent walk in this environment or interact with the 3D environment and things like that. It was part of this course, and that was just so fascinating.

**Kanjun Qiu:**
After you took this course, you decided to do your PhD in a similar field?

**Julian Chibane:**
I also had another course. It was Computer Vision course. It was not so much neural networks and deep learning, it was more of the traditional stuff, our probabilistic view on computer vision. The teacher, he came from the MPI. The course was very interesting for me and it worked out quite well and then my professor told me about this MPI where, all over Germany that's a known institution for doing high quality research. The professor told me about MPI and after my masters, he pointed me towards the MPI and I followed his suggestions and that's how I became a PhD, I guess.

**Kanjun Qiu:**
It seems like you've been pretty focused on 3D reconstruction this whole time so far. What do you feel like has been most exciting to you in the field?

**Julian Chibane:**
Something like the output of a Kinect which gives you a point cloud of a front of a person, for example, which might have some nice details, capturing these details, but also completing the shape of the full human body. That's something I really think is pretty cool.

**Josh Albrecht:**
Yeah. Actually going into, I think it was your first paper, that was one of the things that it looked like it was possible to do. I also, as I was reading that paper, I think probably Julian will do a better job than me at describing the paper, so I was going to let him describe that. That was one of the things that I thought was the most interesting from that. It did such a good job on this. Was actually a really hard problem. You can't see anything in the back, you can't do a normal... You have a surface with a little hole you can smooth over it and fill it in. You can't smooth over the back and fill it in; it just looks really bad.

**Josh Albrecht:**
Do you want to tell us a little bit about that first paper? The title of that one, if I remember correctly was Implicit Functions in Feature Space for 3D Shape Reconstruction and Completion.

**Julian Chibane:**
Exactly. It's about 3D reconstruction. You have some deficient input and you maybe have a point cloud just captured from one side and you're missing the back. Such data can come from X-Box Kinect, for example, which is used for gaming or for a bunch of other applications. There are other scanners also, 3D scanners like LiDAR scanners that are pretty exact but it gives you a sparse point cloud from objects which are further away, and then you're interested in getting the full surface out, things like that. That's the application scenario of the paper.

**Josh Albrecht:**
What was the story behind that paper? When you started your PhD did you join an existing project or you came there and wandered around for a little while, thinking about what you wanted to do, or just random this idea from on high, like "Oh, do this."?

**Kanjun Qiu:**
Yeah, how did this come about?

**Julian Chibane:**
It was my Master thesis. I was going to the MPI and I had several different project proposals from which I could choose from. I really liked that proposal. Initially it was a bit different. It developed during the course of the work.

**Kanjun Qiu:**
What was it at the beginning and then what happened?

**Julian Chibane:**
At the beginning, it was actually using implicit functions. It was a thing already. There were three papers on implicit functions so it was a really early idea, I would say. These three papers were, if I remember correctly, in the same conference at the same year. It was occupancy networks, deep SDF and in that we wanted to build on this idea of representing 3D geometry in order to model garments on top of humans. That was the original idea. We have a human body model, which is parametrized so you can choose the parameters such that you have a specific pose or a specific shape of a person, but this person would not have any clothing on. It would be just a human body model without clothing.

**Julian Chibane:**
Then we would like to enhance that and put clothing on and having a nice representation for that would be very important. That was starter of that idea.

**Kanjun Qiu:**
Then what happened? How did it change?

**Julian Chibane:**
At the end of the day, it didn't change so much. I guess we had humans with clothing but we didn't have this body model anymore in the formulation, but we needed to have a step in between because the problem was these first three papers turned out, not really enabling us to model highly detailed clothing because you have so much information there; you have wrinkles, you have tiny things on top of the clothing and stuff. Also, humans are very different than the datasets that were used within these first three papers. They used mostly rigid objects so something like a car or something like an airplane. That's just so much easier to represent than the human body who can have any pose or any shape, were the first real problem that we had to tackle at that point, and that's what we did with IF-Nets and later on, then we could follow the path on integrating the human body model. But the first we had to solve the problem of reconstructing humans,

**Kanjun Qiu:**
The IF-Nets architecture is somewhat unique. How did you come up with that?

**Julian Chibane:**
First, we applied these other papers, for example, occupancy networks paper and we found that it really has a lot of trouble representing humans because of their variants and poses. We needed to come up with a formulation that somehow used the input data that we have leveraging all the information that is in this input and we felt like somehow the encoding of the inputs in the previous papers wasn't strong enough in order to really nail the reconstruction so we had to change the encoding and that's how we started.

**Josh Albrecht:**
What are some of the sharp edges or parts that you're a little bit uncomfortable? It's still in there or do you feel like it's pretty robust and pretty much done with it?

**Julian Chibane:**
I would say actually it's really pretty robust and that's also why we have quite a few follow-up papers on that. The network has to learn for each point in 3D space. If this point is insights, the object that you want to reconstruct are outside. That's the basic idea of this implicit learning. Instead of predicting the full output at once you predict per point, if this point is inside or if this point in 3D space is outside of the object.

**Julian Chibane:**
It can happen that if you do not sample during training time of the network, if you sample not enough points far away from the surface or far away from the object, the network can be uncertain of the further surrounding and then you might have some artifacts. That's something you can find but it's simple to get rid of those. You just need to sample points there as well and then the network learns not to put artifacts there. That's the only hacky thing that you can find. Other than that, I would say it does what you expect it to do.

**Kanjun Qiu:**
Is there anything you feel like you learned that was surprising from doing this work?

**Julian Chibane:**
How strong the neural networks can be. Yes. We started with simpler tasks for the paper. We started with doing something like super resolution where we had no resolution object and we just wanted to have a bit of a higher resolution of the object and this worked well, but then we started to do some more crazy stuff, as I mentioned, where you just completed the human body, which was not there in any pose of the human body, like an arm is completely missing and things like that. The network really does something very reasonable there so it really learns how a human looks like and should look like. That was really surprising for me actually, that these convolutional layers really do learn something pretty reasonable.

**Kanjun Qiu:**
I was really surprised looking at that result and I was like, "Oh, I wonder was this something that took a long time for you to figure out and get working or was it something that actually the architecture just produced?" It sounds like you were also surprised and so it seems like the architecture actually just learned some reasonable, fundamental representations of the actual objects.

**Julian Chibane:**
Exactly. At least not in that degree. I think it was also, for my supervisor, a bit of surprising. In a lot of research papers you always use the prior of human body models so you have a human body model and then you do something with this. This gives you a prior on how the human looks like. I was thinking that this is something you really need in order to do some good completions, but it turns out the network can really learn a lot of things just from data without using the parametric model.

**Kanjun Qiu:**
Did you ever test it on non-human objects or weird objects like a leaf or nature trees or anything like that? I know those are notoriously hard to reconstruct.

**Julian Chibane:**
We did have quite a bit of experiments on other objects as humans. That's actually something that many people looking at IF-Nets probably miss that it's not only for humans. Basically, can work on a bunch of objects and object classes. We used it on the shape that dataset and the shape that dataset consists of manmade objects; there are cars in it, airplanes and things like that. We use these dataset to show that we're on this rigid objects we can still outperform the prior work and use the human data to show that our approach also working on non-rigid objects.

**Julian Chibane:**
We took part in the ECCV challenge with IF-Nets. Was two challenges; the one challenge was on human data and the other challenge was an arbitrary data. In both cases, it was 3D data of humans or arbitrary objects and the arbitrary object class was really anything, so there were some fuzzy toys in there, there were some computers in there, also some humans statues, anything. We reconstructed those 3D scans, we applied the model, the input was colored 3D scans but with holes either of humans or of arbitrary objects and the task was to complete the surfaces such these scans do not have holes anymore, but also complete the color. That was new. That was an extension of the IFF paper. We extended the reconstruction from only surface to surface and color.

**Julian Chibane:**
Surprising to me was first of all that the color completion is very reasonable. If there's a hole between your shirt and your jeans it will not only complete the surface there but also will complete the colors, the texture, and it will segment your t-shirt from your shorts ad it will look like a reasonable completion also in the texture space. We trained really on these arbitrary objects and we test the model on object it has never seen before, and they had holes, right? The construction still could remove these holes and do a pretty reasonable job although the model has never seen these objects or categories. Even for me as a human it wasn't easy actually. That was also quite impressive and quite interesting.

**Josh Albrecht:**
One of the things I was going to ask about the earlier paper, did you ever try training on the human dataset and then testing on the shape that one or reversed to see how much of the dataset bias actually impacts it?

**Julian Chibane:**
Not on the IF-Net paper but we did something along those lines for the NDF paper and we used a very similar a network architecture so I guess it applies also, to some extent, to IF-Nets. We found that it does generalize quite a bit. Train on shaping it and we tested on real scenes. That's not an experiment that actually made it to the paper, but we tried that just in our experiments and we found that it does quite a reasonable job already.

**Josh Albrecht:**
That lines up with what you were saying about the second paper as well about working on unseen object classes. That's pretty challenging. I think a lot of these 3D reconstruction things that I've seen in the past are like, "Oh yeah, it looks pretty good," but you only train the planes or cars or something so they're all the same anyways. It's a lot harder the other way.

**Kanjun Qiu:**
Why do you think it works so much better than many of the methods out there? Or are there other methods that you feel like, "Oh, this is just as good."?

**Julian Chibane:**
One very important reason is that we include local information of the inputs. If we have an inputs, for example this point clouds of a human, which is where you have the point only in the front of the human, then if we want to reconstruct points near the surface of the human, then we really have local information in the network and the test network, how close it is to the inputs and we have an encoding of this local region of the inputs, but also encode more global information. If you want to complete the backside of a human, you really need to know where you are relative to the input point cloud, which is maybe only at the front. Then you need something very global. The main contribution of the paper is to show how to combine local as well as global information from the input.

**Josh Albrecht:**
That's done with the different multi-level 3D convolutions as well. I think there was some sort of sampling along the axis or something nearby, but just one step in some direction. It's not just looking at the one point, but there's also some points near it or something.

**Julian Chibane:**
Exactly. First of all, yes. We have a 3D convolutional encoding. The 3D input is encoded by using just the regular 3D convolutional network. This convolutional network for each layer of the convolution it gives you a feature grid. It's 3D feature grid encoding your input. The cool thing of these feature grids is that they are aligned with the input which means you know where you find the corresponding feature to one 3D point in space. For one 3D point of space you can look up the corresponding features within these deep feature grids. That's one trick. We can just really look up the features that correspond to your point which you want to decode in the feature grids and then we leveraged our knowledge in the machine learning community that the receptive field is growing, the more layers you have. The early layers we'll have of low receptive field, which means you have very localized informations of your input and the further you go up the hierarchy the more global it will be.

**Julian Chibane:**
We extract features from all the layers, which then yields a encoding of your point, which is global, but also local.

**Kanjun Qiu:**
How are you thinking about follow-up work or building on this? How far can you take it and what are additional problems that you might want to solve with IF-Nets or modifications?

**Julian Chibane:**
We've made some follow up work a colleague of mine but he used IF-Nets and made follow up paper with a variant of it. What he did there is he segmented scans of human bodies into body parts and this helped to register parametric human body model to the scans. Why is that useful to have a registered parametric human body model? It's useful because if you have a good registration, you can then start to move your static scan and instead of a static scan, you then have a dynamic scan, which you can change the pose of, for example. IF-Net was really helpful there in order to predict which body part is present at what location in 3D space.

**Julian Chibane:**
That's one extension of that. That was pretty cool. It was an article in ECCV and he really showed that, then from these static scans, he could really make crazy poses and that worked quite well.

**Josh Albrecht:**
One other question on some of the earlier work in the IF-Nets just in general is how long does it take to train and how long does it take for inference and hey, how long did it take to train? How stable is the training? How long does it take inference time? How much data is in the training set?

**Julian Chibane:**
I see. For the human data set, we used to only around 3,000 scans, if I remember correctly.

**Josh Albrecht:**
Not a gigantic dataset.

**Julian Chibane:**
No, actually not because it's quite expensive to get a lot of high-quality human scans actually. There we used relatively small one to shape dataset that's quite large, but the objects that you have are pretty rigid, pretty prototype-ish, and many objects are near duplicates of themselves. It's a very different setup, actually. It worked on both, we trained one model separately for shaping it and for our humans dataset. Training time is approximately two days if you want to have the best possible quality, or if you want to have the best number at the end of the day in your paper, but the results are reasonable way before that. You can see that it's converging to something very reasonable whether improvements are minor, that's already after some hours.

**Josh Albrecht:**
How many GPUs?

**Julian Chibane:**
We train on a single GPU.

**Josh Albrecht:**
Then similarly for inference as a due to prediction for one model.

**Julian Chibane:**
The prediction of one model is not real time so it's around 30 seconds in order to get your full prediction, which means that's mashed then and that's the final result. The reason for that is the model is implicit, which means you have to query a lot of points. If you want to have a high resolution we use the resolution of 256^3, we have to query a lot of points. For each of these points the network has to decide if the point is inside or outside. The inference time depends highly on your output resolution that you want to have. That's really a matter of what you want to have.

**Josh Albrecht:**
But that's good to have ballpark order of magnitude. I think for some of the NeRF stuff, it took a surprisingly long time to do some of those things, maybe even hours or something. We had to make that little video or whatever. It looks so cool but it took a lot of compute to actually even just do the inference part. For inference, if that makes sense, do you think there's any other downsides of this particular approach?

**Julian Chibane:**
No, actually. I would say that's pretty stable. One limitation and that's addressed with the follow-up work is it's useful to represent objects by occupancy. Is it useful for each point in 3D space classify this point as being inside or outside of the shape? There might be some shapes that just do not separate the 3D space only into two regions inside and outside, but separate the space into more regions and have a layering of surfaces. That it's not really applicable you might have data where you do not really have ground truth inside and outside. It might be that you have holes in your 3D scans so it's not really easy to find out when you are inside of an object or outside of an object. Or maybe you have a thin wall or you have a very paper thin object so that might be very tricky to define inside and outside and that's one limitation that IF-Nets shares with all the other approaches that predict occupancy or predict sign distance because sign distance at the end of the day also has this binary classification into inside and outside.

**Josh Albrecht:**
That idea I think is probably what led to your work at NeurIPS, the Neural Unsigned Distance Fields for Implicit Function Learning. Do you want to talk a little bit about that paper and the approach there and some of the results?

**Julian Chibane:**
It addresses exactly this problem. We wanted to tackle 3D scenes, which often have holes. Often you do not have a fully complete perfect scan of your 3D scene, but you have holes or you have just a partial scan, and it's not really easy to train a model with occupancies where you need inside and outside. That was the setting. What we did with neural unsigned distance fields, NDF for short, what we did there is switching from the SCF representation which is pretty common, so signed distance, to unsigned distance because the sign tells you if you're inside or outside of the object. If you want to get rid of this inside and outside because you do not really have it, it's the first idea of course, to just remove the sign.

**Kanjun Qiu:**
That makes sense.

**Julian Chibane:**
Of course, as trivial as this sounds then at the end of the day, brings some challenges if you want to use this representation, because for SDFs part of the signed distances and for occupancies you have this Marching cubes algorithm, it converts your implicit representation, which tells you inside and outside for each point in the 3D space into something that's more applicable to real world scenarios or use cases, having a mesh. It converts from this implicit representation to a mesh. That's what you cannot really easily do with an unsigned distance field. In this paper, NDF, we showed some algorithms that still allow for visualization for direct rendering into images or to create point clouds, very dense point cloud, so a lot of points describing the surface of the object that you're reconstructing.

**Julian Chibane:**
Also, because we can predict these very dense point clouds, we can then use very classical algorithms that connect these dots and create a mesh from there. We can also mesh then at the end of the day,

**Josh Albrecht:**
For anyone who hasn't seen, it's definitely worth checking it out. The audio description of how cool this paper is doesn't quite do it justice. There's some really great images in there that show how well this works with things that are a lot more realistic. There's a drawing of a bus where there's some seats, it's like a cross-section of a bus. It's really hard to tell what's inside or outside at any of these given objects and it just does a great job of mapping out the contours that feel sort of intuitively correct.

**Josh Albrecht:**
Or there was another really good example. I think you guys had one with a car that had a bunch of internal structure, the internal seats and the windows and the outside of the car and you can see the surfaces for this entire thing. In a way, that's almost impossible to do with these other algorithms that are just looking at the outside of it. It seems much more robust to do things this way. I was very excited about it.

**Julian Chibane:**
Thanks, yeah. Thanks. Appreciate it.

**Josh Albrecht:**
Did you also find it to be actually a pretty useful robust representation and a pretty good extension of these IF-Nets?

**Julian Chibane:**
Yes, I would say so. Especially if you have these scenarios where you do not really have inside and outside so there it's really applicable. But of course, if you have inside and outside and you have this ground truth data, then you can just go with the classical style of a occupancies, and then you can rely on Marching cubes which is well-developed and fast and that's also a very valid approach. It depends on your scenario.

**Josh Albrecht:**
I think the exciting thing for me in a lot of real-world scenarios is really hard to get the inside and outside, like Kanjun's example earlier about the trees or leaves. Yeah, sure there is an inside to a leaf, you really don't want to be representing that.

**Julian Chibane:**
Exactly.

**Josh Albrecht:**
Or cloth, right? Or a scan of a room. Yes, there's technically an inside and outside but you're not going to walk through the other side of every single wall to have to get the outside of the entire thing, it's so obnoxious. It's really nice to be able to not worry about that in a practical setting, I think a lot of cases.

**Kanjun Qiu:**
If I were a practitioner and I was deciding between these unsigned fields versus a signed field, when would you recommend I use one or the other?

**Julian Chibane:**
As soon you have ground truth for occupancies I would go for that because you can really use these classical Marching cubes, which does a great job in creating surfaces because most applications scenarios at the end are interested in having a mesh as an output because it's very lightweight. You can also get this with NDFs, but you have to do a step in between. First you predict a very dense point cloud and then you mesh. That takes more time. Therefore, if you can use occupancies and if you have good data and no holes and high-quality data and everything is perfect, then of course go with the easy approach. But for a more real case scenario, the NDF approach would be the thing to go with.

**Kanjun Qiu:**
If I don't care about meshes at all and I maybe only care about representation of objects, then the NDF approach is a good one to go with?

**Julian Chibane:**
Yeah. Then in any case, so if you were interested in images, so if you want to render or if you want to have a point cloud that's perfect, yes. Or again, if you want to have meshes but you do not have ground truth with occupancies then still NDFs is the way to go.

**Josh Albrecht:**
One other thing that I thought was pretty cool about the paper was the connection to progression. The experiments at the end with just random 2D point data and lines and things like that, I thought that was a really interesting idea. Do you think that's practical at all? Maybe it's also probably worth describing what exactly some of those setups were and how that worked. But then also the question is, is this practical or useful in any setting or is it just a neat trick?

**Julian Chibane:**
Yeah, I've actually also been very excited about this but reviewers didn't like it so much. I didn't appreciate this idea of doing something that's coming originally from computer graphics, which is Ray Tracing and then using Ray Tracing for regression. It's just an interesting connection, right? To the applicability, we didn't do very thorough experiments on any kinds of regression or function that you could regress. Representing functions as unsigned distance fields is actually really a very interesting in doing this regression with this Ray Tracing idea. I think it's really worth looking into this and maybe following up on it, because I think with this formulation the neural network can really represent any function or also other 2D surface.

**Julian Chibane:**
Functions are not so complex; you could have a binary classification, everything above the function is inside, everything below is outside. You could do that, but there might be some curves that do not really define an inside and outside like a spiral, for example. If you apply neural networks to learn to connect these surfaces using this implicit approach, that's very exciting.

**Josh Albrecht:**
Are you currently doing any all board?

**Julian Chibane:**
Everybody can follow up on these, I guess.

**Kanjun Qiu:**
Switching topics a little bit if you're done with the papers, one thing I'm really curious about is in this field whose work has impacted you the most?

**Julian Chibane:**
I would say it's these three papers that I mentioned; it's occupancy networks from Andreas Geiger's group, from Latz as a first author, deep SDF and IMNET and also Pifu, of course. Let's not forget about that one. They made it popular because it's not really true that these are the first papers. There's a paper which is one year before them, and it's never cited, but it actually does everything that we are in this implicit realm are doing. It's called Deep Volumetric Video From Very Sparse Multi-View Performance Capture. It's a paper from Hao Li from Hao Li's group. They actually already do all these things. They predict in a point wise manner inside and outside and then they do Marching cubes to get a mesh and they predict this from images.

**Julian Chibane:**
The idea was there one year beforehand, but it got popular only with these three papers, I would say. I guess none of these papers actually cite that paper. At least, I would say it's underappreciated.

**Kanjun Qiu:**
When you first digested these papers and felt like they were very impactful, what were the key salient points that you got out of it? How did it change your view?

**Julian Chibane:**
I was doing my master thesis so it forced for me really the first time getting into this 3D vision research. It was not so easy to understand the impact this really has. I'm not sure if other people were so certain of the impact of these ideas, because I would say now with one or one and a half or two years after these papers, I would say they had a really significant impact in representing 3D scenes. I'm not sure if this was clear at that point already, these many follow up papers that use these ideas for other stuff and then show that they are applicable, of course, our paper IF-Nets, and many others they really made a success out of this idea and NeRF, right? That was this big paper everyone's talking about and these next conferences will probably mainly be NeRF conferences. Yes. Also builds on this idea of predicting point-wise so it was really impactful.

**Kanjun Qiu:**
How does [inaudible 00:28:32] thinking impacted you? Just generally the methodology of predicting point-wise is really what it told you like, "Oh, this is something I can take further."

**Julian Chibane:**
Yes. That was breakthrough in representation of 3D scenes because representing 3D scenes it's not so easy as representing a 2D image. For 2D images we know how to represent them; we use grids and for each point in the grid, we have the RGB value stored and that's it. We all agree that this is a good representation for an image, or at least maybe not all of us, but it's a very common representation for an image. But that's a bit different for representing 3D scenes, especially for learning because if you want to learn, it's not so easy to learn with a mesh, for example. Mesh is a very dominant representation of 3D surfaces, but it's not so easy to learn with those; you're applying a neural network and things like that.

**Julian Chibane:**
That was why these implicit papers had such an impact because this representation wasn't so clear or it's maybe still not so clear and that the major drawback of this volumetric approach where you extend a 2D image to 3D by just concatenating a lot of images, one after another, and then interpreted as a 3D volume so you have a voxel grid. This approach is really memory intensive so you have to start a lot of values and that's not so easy to do on our GPUs. Maybe in some time in the future we will go back to voxel but currently, although our hardware resources are increasing, that's not that easy so that's why there is such a success of this idea.

**Kanjun Qiu:**
It seems like voxels, I guess my opinion maybe, it's the discreet representations are definitely non-ideal and this is an issue with 2D as well.

**Julian Chibane:**
Probably not the hierarchical wheel in our brain. We are focusing on where more details are.

**Kanjun Qiu:**
To your point there, I think there is something really interesting about how do we decide what to pay attention to and then how do we register detail in the area that we choose to pay attention to. It's a little bit separate from the representation that we use.

**Josh Albrecht:**
Some of the implicit priors captured in the work that you did and that's even in unsigned distance fields, I noticed there's forcing it to pay attention to the region that's very close to the surface and spend most of its resources there as opposed to, I don't want to be encoding. "Oh yep, still air. Yep, still lots of empty air."

**Julian Chibane:**
Exactly.

**Kanjun Qiu:**
One thing I was curious about in this field in general is what are some of the most important open questions that you feel like as a field it's important to address?

**Julian Chibane:**
It's not really real-time. At inference time, we still discretize so we still are creating a voxel grid then at the end of the day. We just defer it, we do not do it in the learning phase and we're not storing this voxel grid within the GPU, but we are predicting at the end of the day voxel grids point by point in order to then apply Marching cubes, for example. That goes for this implicit function work. In NeRF of course, we're doing it differently but also if we have to query many points in order to render an image, for example. One crucial aspect of the next time will be how can we do this more efficiently? Coming back to our example, if we are in 3D space we do not need so many samples there, right? We do not want to sample many points in the 3D space of air where nothing is and we have to find something more clever neglecting free space, for example and paying more attention to surfaces.

**Kanjun Qiu:**
Paying more attention to services and even more attention to where there's a lot of texture or something like that.

**Julian Chibane:**
Exactly. It might not be always as easy as that if you want to represent something that has no surface or no clear surface, something like fork or something volumetric, then you need also samples in free space, or then it becomes ambiguous what is free space and whatnot. But maybe sampling more points where you have a higher density of objects.

**Josh Albrecht:**
Or maybe it's simply more points where it's more important for some downstream task like using attention to allocate towards, do you want to pay attention to the rough shape of this object or just this little particular piece over here or that sort of stuff as well.

**Julian Chibane:**
Exactly. There's quite a bit of work to be done there because of course, it would be cool to have these upsides of these predicting point-wise to have this also in real-time applications such that we can really use these things instead of just having ex-research results. Maybe one question should be go back to the previous question because there are, of course, more things that can be done, for example, making this implicit representations more interpretable or more interactive, and people are starting to work on this already. If we think of NeRF, which is learning some continuous representation based on images, then it would be cool to have this scene representation more interpretable, more interactive s to be able to relight a scene would be very cool, there are papers coming out in this direction.

**Julian Chibane:**
But of course, also maybe changing the pose of objects or changing the pose of humans maybe, it's interesting as well. Not only capture the real world but also being able to manipulate, maybe capturing the real world or the scene of interest at different timestamps maybe if an open scene is rainy, for example one time it's sunny, and then maybe being able to interpolate between the settings of your scene and interactively manipulate the scene, I think there would be so much cool opportunities. It would have so many applications for gaming, for example, maybe creators can capture more of the scenes instead of recreating or artificially doing some things like that.

**Kanjun Qiu:**
What is the current state of interactive scene representation and being able to modify some of these parameters?

**Julian Chibane:**
There are follow up papers on the NeRF representation allowing for relighting and other papers looking into dynamic scenes. There is work on that but we can still explore this direction much more in order to really elaborate stuff.

**Kanjun Qiu:**
What are you interested in here?

**Julian Chibane:**
Actually, this relighting before I've seen the paper that it's already being done. That was something I wanted also to look into but using these representations for larger scenes, for example, is also something interesting and for large scenes making them as dynamic and as interactive as possible, and also doing augmentation, putting different objects into the scene.

**Josh Albrecht:**
Thinking about how to make a larger scale practical version, where you can swap out the objects and change the location and change the general parameters of the scene and things are able to deform. It's like a really robust, good, large scale scene representation would be really interesting.

**Julian Chibane:**
Something we have for our human body models, which are of course hand engineered, but maybe discovering some latent parameters maybe of scenes and then manipulating those different styles of the scene or object.

**Kanjun Qiu:**
That'd be so fun as a designer.

**Josh Albrecht:**
Yeah. That'd be super fun to play around with.

**Kanjun Qiu:**
Find the line between the real-world and digital objects.

**Julian Chibane:**
Exactly. Maybe effectively helping creators to less focus on some redundant work, but put more attention on the creative aspects of their work where they can easily get a sunny scene or any scene. Stuff is just handled by cool mechanism in the background. That could be something very cool.

**Kanjun Qiu:**
There was an Adobe paper demo where they're doing retexturing, relighting of nature scenes.

**Josh Albrecht:**
That one specifically was separating the appearance of the scene and the structure-

**Kanjun Qiu:**
From the structure of the scene.

**Josh Albrecht:**
... of the scene for 2D images so they were able to very quickly swap out [crosstalk 00:35:56] like mainly Sony-

**Kanjun Qiu:**
That's true. You're right.

**Josh Albrecht:**
... or take the mountains over here and put them over here and controlling those things separately with a brush being able to select the thing and paint it somewhere else. It's pretty interesting.

**Kanjun Qiu:**
It is really cool. It'd be really cool to be able to do that in 3D.

**Josh Albrecht:**
Exactly. Yeah, it'd be great to see in 3D,

**Julian Chibane:**
I guess that's not the only thing that would be nice to transport from 2D to 3D. There are many cool ideas in 2D that we would like to have in 3D. This 3D field has a lot of potential to grow and there are many applications that really use and really need these 3D representations. Exploring this more and more how to get information from the real world into the 3D representation and allowing to use this real world information to design and to alter 3D representations and to apply them to different use cases.

**Kanjun Qiu:**
What are some controversial opinions you have about research or fields that you feel like other people don't necessarily agree with?

**Julian Chibane:**
One argument that can come up in rebuttal, for example, when you have to defend your research or people around me defend their research is that the approach is simple. Sometimes that's criticism actually. The idea is simple. It's too simple or something. That's something which might not be that good actually because simple approaches, that's not a bad thing, that's a good thing. It's a good thing to have something simple as long as it does something reasonable, as long as it really helps. We do not really want to have very elaborate architectures with a lot of parameters doing something, it's a black box we don't really know. It's better to have something simple and to make simple ideas work and to do some things in smaller steps but really understanding.

**Josh Albrecht:**
I couldn't really agree with you more towards this opinion over time. There's no need to add any extra complexity. We barely even understand how or why neural networks work. I think the idea of taking the sign off of a sign distance field and making an unsigned distant field, I think that's great [crosstalk 00:37:47].

**Kanjun Qiu:**
That's brilliant. Why didn't the people who were working with sign distance fields think about that?

**Julian Chibane:**
I've been with the claim that we're the first using unsigned distance fields, so...

**Kanjun Qiu:**
[crosstalk 00:37:56].

**Josh Albrecht:**
Making it actually work and showing how well it works and where it works and getting it to work for rendering and for meshing and all these other things. I think that's very valuable. It's a simple idea but there's a lot of work that goes into making it really actually work.

**Kanjun Qiu:**
In product development we have a saying that there's this curve of how much effort you put in. If when you have put in very little effort, then your work is basic and when you have put a medium amount of effort your work is complex. Then when you have put in an enormous amount of effort your work is simple. Simple [inaudible 00:38:26] it's not at the beginning. That's true in a lot of design disciplines, which research it because it's a creative discipline.

**Julian Chibane:**
Actually, this goes not only for the idea themselves but also for the presentation, I would say. That's not so much in the English language actually but for writing in German, people often disagree. I really had to relearn how to write the bits in English because it's very different actually. In German, if you state the sentence already should reflect almost all possible circumstances, it should reflect the full truth, and of course makes the sentence very large you have to use a lot of commas, and it's very hard. You have to have really complex sentences in order to nail down what you want to say. That's very different to the writing in English and I really enjoy that.

**Julian Chibane:**
I just had the discussion with a friend of mine who's writing his master thesis. People in Germany sometimes really tend to have these really large sentences and make really hard to understand texts which are, of course, they are very to the point still, they are very exact and it's very expressive. These are definitely upsides but for a reader, at the end of the day it's really just hard to parse. You really have a hard time understanding what the people are trying to tell you. I really like this also this idea of simple is better, it also goes for me in writing and even if I write German now, I write very short, clear sentences if people like it or not.

**Kanjun Qiu:**
Yeah. I have this theory that constructing good explanations of things is almost an entirely separate discipline than making forward research progress and doing novel work. The field needs both to push the novel work forward and also to construct a ladder for other people to understand what the novel work is, otherwise you end up with too much understanding debt with very difficult for people to really know what's going on and at some point it becomes very hard to make progress. What other controversial research opinions?

**Julian Chibane:**
Another thing is that I really tend to like small steps and research better than having highly engineered really big architectures that solve one task very well, but it's not really interpretable where this is coming from. I think that's why NeRF is so popular, actually. It's because it has a very simple representation, it uses stuff that's absolutely clear to readers, for example a fully connected network. That's very clear for readers what that is so they really just use this representation and show that it really is powerful. Also, including volumetric rendering which is also known so they really take key things that are known but do something very important and very helpful with it. They have something which is very clear why it's working and why it's not working instead of sometimes you have papers solving some task but they have four different networks in there, even do not have any real names, they're just doing something not interpretable and yeah, I really tend to have a hard time parsing those papers.

**Kanjun Qiu:**
Josh is really on this side of small modular networks, no giant big architectures.

**Josh Albrecht:**
Mm-hmm (affirmative). I think it's also interesting to see what happens when you take all of these small things and put them together in some other larger way. Before you do that, you want to understand what are each of these pieces for and why are we really doing this and the resulting work. It can be really hard to interpret what the different contributions of the different pieces are, unless if you're just taking one fully connected network and something, "Okay, sure we have [inaudible 00:41:48] what's contributing what at this?" I think my favorite though, are the ones that are simple approaches and they get great performance, like the IF-Nets, for example. It's a pretty simple approach, works really well. I think it's always interesting to see you when you can take something so simple and make it work so well.

**Julian Chibane:**
But of course, that's not always easy to get there and I guess also it depends highly on where the research of the field is. At some points, you just have so many papers already solving problem A and then the next paper of course, has to beat a very high baseline already so it's much, much harder to make big steps there, it's very valid to have larger capacity models or more engineered models. I fully agree with what you said, it's good to start small, right? Try to have a good understanding of what you're doing or what your model is doing and then start to extend the complexity, but maybe not start with a very complex model at the beginning.

**Kanjun Qiu:**
What do you think is something you've learned or something you've observed about what makes a great researcher great that would be unusual for other people to say?

**Julian Chibane:**
Being patient with other people's ideas, being patient listening to other ideas and first trying to understand theirs before pushing your own or before fighting for yours or having patience also to develop your own idea, taking your time to do the things that you want to do.

**Kanjun Qiu:**
How did this come to you? Were there some experiences where you learned, or you were not as patient before?

**Julian Chibane:**
Yeah. Starting with my master thesis, I was quite anxious to get some results, but then the course of the work changed; it wasn't as predictable as hoped that we could just engineer the architecture and everything is working out at the end. It's not really like that. I had to adapt to change the setting as it wasn't so easy for me, but being patient helped and of course, also having people who believe in you telling you that what you're doing is still worthy after coming up with this IF-Nets, but having had a different goal it wasn't so clear for me at that point after working so much that this is still something useful. But then you have to be reminded again, that if you change the setting, this is really useful for other people or for a different setting. That was also something I'd learn.

**Kanjun Qiu:**
There are these like troughs of sorrow, "Oh, I'm so excited about this. Oh, it doesn't work," and having someone to pull you out of the trough of sorrow is very valuable.

**Julian Chibane:**
Yeah, maybe focusing on the positive sides also that's something which can make great people great. Many people tend to try to, if something is not working to improve what is not working. They forget that other stuff is really working well and instead of pushing what's working they try to engineer what's not working. Maybe sometimes shifting the focus is also very helpful.

**Kanjun Qiu:**
[inaudible 00:44:27].

**Josh Albrecht:**
That resonates with me. It's about being open to finding these new things. I think some of the most-

**Kanjun Qiu:**
Focusing on strengths.

**Josh Albrecht:**
Yeah. Some of the most interesting discoveries also come from, "Oh, we were trying to do this thing, didn't really work and it kind of worked but we noticed that this other thing over here was really interesting and so we just went off in this other direction."

**Julian Chibane:**
That's also what research somehow should be, right? In research if you already know that everything is working beforehand then it's not really research.

**Kanjun Qiu:**
It's a discovery process.

**Julian Chibane:**
You have to be open for this discovery process, which is not always as easy as it sounds.

**Kanjun Qiu:**
Totally. Yeah.

**Josh Albrecht:**
What are some tips or tricks or hacks that you've learned?

**Julian Chibane:**
If you start a project it's always good to start with the smallest possible architecture or the smallest possible portion of your idea. Even though you have a much higher goal that you want to achieve, A, B, C, and D you start just by achieving A and trying to figure out what needs to be done to do this, instead of trying to hammer the full problem at once. If you do it like that, it's also much easier to test your assumptions, to test your code because many ideas fail or do not really come up that well because maybe there's some implementation error or there's some error in your formulation and you really need a small formulation or a small project in order to track down such issues and then develop your problem further based on what you've learned in the beginning. Simplifying your own idea at the beginning of the project is something very helpful.

**Josh Albrecht:**
That also resonates with me; having something nice and simple to start with is a great place to start.

**Kanjun Qiu:**
Did you apply this in either of your papers and how did that work?

**Julian Chibane:**
This strategy I'm applying it in each paper always. I always try to start the smallest possible portion of the idea or with the easiest setup. Even if I want to tackle a very complicated setup, I would try to first use it on the easiest setup and check what difficulties might be there that I need to solve.

**Kanjun Qiu:**
I was just going to say for IF-Nets, for example, if you had to get just very concrete what was the easiest setup?

**Julian Chibane:**
The easiest setup there was comparing if these occupancy networks results, for example that cannot really represent humans, these humans had missing arms, for example. From the input that we had it was maybe a course human. If we just interpolate the information that we had there with a very, very tiny network or no neural network at all, if we interpolate these input information, shouldn't this already give you much more accurate pose of the person? In the input there is some arm, for example that occupancy networks, for example is missing. If we do some simple interpolation shouldn't we get there something more reasonable already by just paying more attention to the data, without even doing a very large learning machinery, relying more on local features?

**Julian Chibane:**
That was the place to start with there and then we wanted to extend this, we wanted to complete shapes so we had to use also more global features and then we really used the 3D scene.

**Kanjun Qiu:**
That's a really simple starting point.

**Josh Albrecht:**
Are there any ideas that you thought should work that did not work as you expected?

**Julian Chibane:**
Yes. One further goal was to go from this unsigned distance field to a mesh directly, having a variant of Marching cubes which can do it for occupancies but doing it on NDFs. You have the unsigned distance field and still, you want to mesh it directly using some variant of Marching cubes. We've worked on that and we found some reasonable results, but it was still creating holes here and there and it wasn't really working out all that well. We didn't put it in the paper so I guess this was something I imagined to be easier after having quite good prediction, but this hand engineering should not be underestimated so having a good head engineered algorithm that really nails the meshing that's not to be underestimated.

**Josh Albrecht:**
One thing we generally ask is, are there any things that you would like other people to reach out to you about looking for collaborators or specific ideas or projects?

**Julian Chibane:**
Yeah. The things that we talked about, these applications of 3D scene representations, their use cases or the further development that's what I'm really interested in. Especially also incorporating some geometric or some physical principles within those ideas, that's something I really like. People interested in similar things are always welcome to contact me and I'm very happy to look for collaborators to work on cool stuff.

**Kanjun Qiu:**
Awesome.

**Josh Albrecht:**
Great. I really enjoyed our conversation today. I think there was a lot of really cool stuff in there and the papers are great. I would encourage anyone listening to go check them out because our descriptions don't necessarily do the pretty pictures justice. You have a code online for all of them, I think as well.

**Julian Chibane:**
Yes, yes.

**Josh Albrecht:**
Which is also great, I always really appreciate that. If people want to go play around with them, it's all there. I really enjoyed this and hopefully people listening to it too.

**Kanjun Qiu:**
Thanks so much for chatting with us.

**Josh Albrecht:**
Yeah. Thanks a ton, Julian. This is great.

**Julian Chibane:**
Thanks. I enjoyed it too.

**Kanjun Qiu:**
Thank you for listening to Generally Intelligent. We love feedback and questions so please feel free to ping us on Twitter at @Kanjun and @JoshAlbrecht or email us with any ideas or corrections. If you enjoyed this podcast, please share it with fellow researchers, rate it on iTunes and follow us on Spotify for your favorite podcast app. Thanks very much and we'll see you next time.

