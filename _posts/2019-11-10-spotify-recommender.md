---
title: "Spotify Song Recommender"
layout: post
post-image: "https://images.unsplash.com/photo-1484704849700-f032a568e944?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
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

--
<h3>Recommendation model using Spotify songs and features</h3>
--
---


[See the work](https://github.com/claudiasofiaC/spotify_nn)
--
---

Implemented a K-nearest neighbors model to recommend songs to users based on their profiles. The features that make up a song are unique to Spotify.

Songs were recommended based on how alike they were based on selected features.

Spotify engineers their own features and while they might have funny names, the features are great metrics to compare songs to one another.

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



