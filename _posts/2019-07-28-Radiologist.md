---
layout: post
title:  "Creating a Radiologist from Scratch"
date:   2019-07-28 17:04:01
categories: post
---

I had no idea how to do it.
I had never looked at an x-ray other than my own, more so at an x-ray that showed some physical defect. I did not know what to look at to determine a defect. How could a person with zero experience in Radiology tell a machine how to look at x-ray images?
<!--more-->

Six hours later, I still didn’t know how to determine if there’s a defect. But somehow, I was able to create a machine almost as good as a Radiologist at detecting a defect.

## Which x-ray shows a disorder?
I was skimming through my laptop screen trying to get a sense of the web page in front of me. There were two folders: both contained the x-ray images. Some images were labelled positive and some were negative. I took one out from both labels and I honestly couldn’t tell the difference. Beside me were my nine teammates, two of which were working on the same problem. As the only undergraduate student (and the only one without any formal instruction in college mathematics save for that one calculus course), I was surrounded by either graduate students or professionals working as data scientists, data engineers, and public health researchers.

We were working on creating a machine that can classify if an x-ray scan contains Pneumothorax (basically, a collapsed lung) and then identify where in the image is the collapsed area. Aside from not being able to tell the difference, we had to find a way to show which area in the image had the difference. While the images may have labels, it doesn’t have labels on which area is the Pneumothorax present. While we had two people who have experience in Radiology on our team, surely we couldn’t rely on them to tell us where precisely the affected area was in more than the 3,000 Pneumothorax- positive images. As the final personal obstacle at my first datathon, everyone was using Keras while I was using Pytorch, both frameworks for Deep Learning. For the most part, we could not understand each other.

Again, aside from not being able to tell the difference, we had to find a way to show which area in the image had the difference. You’re asking a blind man to teach a machine how to ‘see’ and look at an image to determine if it’s positive for Pneumothorax or not. On top of this, the closest help you can get were working in two different coding frameworks which made it feel like we were talking in two different dialects. And then we somehow had to miraculously overcome this situation and combine whatever we built with a system that will potentially be used to save a human life. This is crazy.

You’re asking a blind man to teach a machine how to ‘see’ and look at an image to determine if it’s positive for Pneumothorax or not.

## Baptism by Fire

Our group’s presentation at the National University of Singapore (NUS)-Massachusetts Institute of Technology (MIT) Datathon

The problem was split into two parts, classifying and segmentation. A classifier task is classifying images according to their labels (e.g. whether an x-ray image shows a case of Pneumothorax (positive) or not (negative)), while a segmentation task is identifying which part of the image has the object in question by segmenting the image into ‘parts’ (e.g. if positive, the positive area would be given a boundary that separates it from other objects within the image). I volunteered for classification because it seemed easier.

Since we were coding in different frameworks, I had to make my own classifier. In our team of three, we were to compare our classifiers and select the one with the best accuracy. One of my teammates was working with pre-processing x-ray images as a job. As a final caveat, I had only begun learning Deep Learning two weeks before, and I had never made a real model just using Pytorch either. At the time of this writing, I still haven’t used Pytorch exclusively (but I’m getting there!).

Instead, I’ve only used fastai which is built on Pytorch. It’s a beginner-friendly library that simplifies the entire process of loading an image dataset, training it on a deep learning model, and then using it to predict the label of new images. They also have a full course online, and I used the first lesson as a guide to make my first image classifier. But that was my first and only classifier that I built before joining this datathon.

So with nobody else to ask how to implement this in Pytorch, I simply copied the steps of my first project. I took the provided image dataset from the Society for Imaging Informatics in Medicine (SIIM) and remotely connected to a GPU from the National Supercomputing Centre Singapore (NSCC). I used my knowledge of Excel manipulation with Python to clean the labels file (and it still took me more than two hours to find a the simple formula to change all non-zero values in a column to 1).

I used this dataset to train the model on a Resnet-50. The Resnet-50 is a model/ neural network that was shown millions of images previously to produce a series of ‘weights’. You can think of weights as a set of numbers that represent the strength between neurons in a model that help the model ‘look’ at an image. The intuition is that using the Resnet-50’s weights is better than using randomly picked weights because the model is already better at ‘looking’ at images. This process is called transfer learning. For another analogy, it’s like a teacher (pre-trained model) transferring knowledge to a student (new model for the specific problem).

There were 4 different sizes for the same image. I started with the highest resolution of 1024 x 1024 pixels because a higher quality image can help the computer ‘look’ at it because it’s clearer, right? This process took one and a half hours while almost burning the GPU given to me.

Fit one cycle policy is a learning acceleration technique, but running on 1024 x 1024 still took almost 2 hours :(

I literally fed a total of around 44, 000 HD images to the computer. But surprisingly, the accuracy was 86% with the default settings. In the end, I had to abandon this approach because my GPU frequently ran out of memory.

I was 6MB away from remotely crashing a foreign government’s hardware

## Learning by Itself
It’s amazing that it reached 86% accuracy in the first place. It’s better than a guess, and probably better than my ability to look at x-rays. But how did it get there? I did not give any instructions or hints on how to look at the images other than saying which image is positive or not for the training test, but it was able to predict on the validation set without labels. How did the machine learn how to learn?

To abstract ideas out of experience and observation is the fundamental characteristic of learning, and machines are getting better at it.

Look at how this model got here. The source of a machine ‘learning’ is feeding it examples. From examples, like a human recalling experiences, it is able to find patterns. It’s not rote-learning because it’s able to generalize and be applied to new and unseen data. I did not code anything explicitly telling it how. It developed a rule by itself. To abstract ideas out of experience and observation is the fundamental characteristic of learning, and machines are getting better at it. So how could I, with zero experience in Radiology, tell a machine how to look at it? I didn’t, and that’s precisely why it learned.

Going back, I was forced to use smaller images, so I opted for the 512 X 512 image size. I was surprised how faster it was compared to the previous run:

My model achieved almost the same accuracy ten times faster. Wow.
I was wrong. It can classify better at the same epochs compared to the previous version and almost half the resolution. My intuition was broken. Perhaps the model didn’t had to have looked at unnecessary details that made the higher resolution present. If only I did it for another epoch, I could have gotten a higher initial accuracy. I spent the final hours tweaking the model to improve it.

The final version of the model. I actually got 89% accuracy but I wasn’t able to save the version.

In the end, my classifier performed the best (the next one had ~71% accuracy), and it was combined with the segmentation model to complete the Pneumothorax detector. I had managed to use my scarce knowledge in deep learning to make a model that outperformed the other models made by professionals. This model wasn’t built on sophisticated pre-processing techniques nor on elegant algorithms. Merely following some simple techniques showed and surprised me that I was able to build a model that can perform competitively and accurately.

## Still a Noob

But along the way, I owe support from my teammates. I had asked the doctoral CS student to help me with Python callbacks and trying to override some pre-built functions in the fastai library. I got tips on how to pre-process the images (which unfortunately, I wasn’t able to implement because I did not know how to code them) from the medical imaging analyst. I got help from our radiologist on how to identify where the Pneumothorax is manually. I also got help from a data engineer on how I can see what the model ‘sees’ through a heat map. There’s still a lot of areas where I could improve the model, but I wouldn’t have been able to build one in the first place without them.

Grad-CAM: Where the model “looks”. (Middle) The hotter the area is, the higher focus of the model on that area. Notice how it ignores the labels and arrows on the side. Our radiologist confirmed that the Pneumothorax was within the hot area. (Right) The image in grayscale.

Most importantly, they shared their stories on how they got into Machine Learning. While most had the appropriate analytical backgrounds, such as degrees in biomedical engineering, computer science and pure mathematics, nobody learned it in the classroom. Whether it was a way to automate their tasks or augment their research insights, they were able to teach themselves by taking online courses, getting online certificates, and competing in Kaggle competitions.

We’re in this period where there are many unexplored areas for AI systems to be developed, and we’re in the process of realizing the potential to improve our quality of life.

This lack of availability of formal training and the existence of the Pneumothorax problem reflects the overall state of applying Artificial Intelligence as it currently transforms how we work. We’re in this period where there are many unexplored areas for AI systems to be developed, and we’re in the process of realizing the potential to improve our quality of life. Looking at the Pneumothorax problem alone, someone will develop a solution that won’t require a radiologist in the process in the same way an autonomous car doesn’t need a driver. Again, this has enormous applications in places that lack radiologists. Extend this to specialized jobs with scarce manpower.

However, again, this extends to the harms such as reduction in labor and the lack of retraining for displaced workers, the use of AI to make unethical judgments, and the use of AI systems to target disenfranchised groups that perpetuate social and capital inequality. These will eventually become part of the main issues ordinary people will have to tackle in a similar way as poverty and politics, as it’s only a matter of when such systems will dominate our lives in the same way the internet shapes most people’s interactions with reality.

The last thing this situation showed me is that the classroom is just isn’t enough to learn about the world. It is never enough to have just the theory, and as long as real-world change with unique and unseen problems happens faster than the change in classroom instruction, the classroom curriculum won’t catch up.

You can have a background just as many people in my team did, but it can only give you an edge on certain areas. From gathering information, to training the model, and to visualization, these require specializations that usually cannot be done just by a single person. You’ll need expertise within an area along with the flexibility to collaborate and understand other disciplines. These people took the time to learn Machine Learning because they realized it’s a tool that can help them.

Like them, I’ll continue to learn and keep on practicing. Hopefully this isn’t the only thing I train from scratch.
T
he code I used is available as a jupyter notebook on my repository. Check it out!