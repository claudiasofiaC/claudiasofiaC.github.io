---
title: "Facial Recognition/Detection"
layout: post
post-image: "https://images.unsplash.com/photo-1519313825-713a373f2bce?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1075&q=80"
description: Using OpenCv and my webcam to recognize and detect faces.
categories: 
- data visualization
- OpenCv
- Python
tags:
- Python
- facial recognition
- webcam
- machine learning
author:
  display_name: Claudia Chajon
  first_name: Claudia
  last_name: Chajon
permalink: "/2021/03/20/facial-recog/"
---
<h3>Facial Recognition using OpenCv</h3>

[See the code](https://github.com/claudiasofiaC/Facial_Recognition_Attendance)

A facial recognition/detection project using OpenCV and my webcam. Images of people are encoded and detected, then the names of the subjects in the images are added to an “Attendance” sheet at the time they were detected. Usually I see facial detection projects that use popular tech people as the test subjects, I wanted to apply that faces of people I actually know.

I definitely did not use the most flattering pictures of the people that I know, but I did not want to make it easy for the algorithm to detect a face. However, I will not be sharing those pictures and results.

<h3>Image used to train model</h3>

[mads](/assets/images/blog_post_images/mads.jpg) [coel](/assets/images/blog_post_images/coel.jpg)

Using one image of Mads Mikkelsen to train the model and identify key and unique facial points, the model can then correctly identify a new picture of Mikkelsen.

<h3>Successful Detection</h3>

Attendance is taken and marked as a subject is recognized by the program using OpenCV and Python. Subject is identified, their name is shown on screen and then added to the attendance sheet.

[mads_det](/assets/images/blog_post_images/mads_det.png) [coel_det](/assets/images/blog_post_images/coel_det.png)

New faces will be added to the attendance sheet as they 'show up'. Faces already recorded as present, will not be marked a second time.