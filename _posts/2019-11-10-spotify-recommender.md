---
title: "Spotify Song Recommender"
layout: post
post-image: "https://raw.githubusercontent.com/thedevslot/WhatATheme/master/assets/images/SamplePost.png?token=AHMQUEPC4IFADOF5VG4QVN26Z64GG"
description: Program project, build a recommender system to recommend similar songs using Spotify's API.
categories: 
- machine learning
- recommender system
tags:
- recommender
- Spotify
- machine learning
author:
  display_name: Claudia Chajon
  first_name: Claudia
  last_name: Chajon
permalink: "/2019/11/10/spotify-recommender/"
---
<h3>Recommendation model using Spotify songs and features</h3>

[See the work](https://github.com/claudiasofiaC/spotify_nn)

<p>Implemented a K-nearest neighbors model to recommend songs to users based on their profiles. The features that make up a song are unique to Spotify.</p>
<p>Songs were recommended based on how alike they were based on selected features.</p>
<p>Spotify engineers their own features and while they might have funny names, the features are great metrics to compare songs to one another.</p>

![features](/assets/images/blog_post_images/spot_features.png)

### Features includes:
- danceability
- energy
- acousticness
- instrumentalness
- liveness
- loudness
- speechiness
- valence

These four radar charts show 4 different songs that the KNN model found to be similar in features.

![charts](/assets/images/blog_post_images/songcomparison.png)



