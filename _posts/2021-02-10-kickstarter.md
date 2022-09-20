---
title: "Kickstarter Success/Failure"
layout: post
post-image: "https://images.unsplash.com/photo-1561414926-7f3f921a2e18?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=736&q=80"
description: Using machine learning to predict success of Kickstarter campaigns.
categories:
- machine learning
- Python
tags:
- Python
- data analysis
- data visualization
- machine learning
author:
  display_name: Claudia Chajon
  first_name: Claudia
  last_name: Chajon
permalink: "/2021/02/10/kickstarter/"
---

<h3>Using machine learning to predict successful campaigns</h3>
--
---

[See the work](https://claudia-chajon.medium.com/kickstarter-to-succeed-or-not-to-succeed-9c0ca2f665f0)

--
---

[Kickstarter](https://www.kickstarter.com/) is a company that allows creative projects to come to life through crowdfunding.


People who become project backers are offered perks as rewards for pledging money towards the project. These perks are incentives to bring in more backers and thus fulfill the monetary goal of the project.

Within these 15 main categories, there are various sub-categories that further identify a project.

From inception, Kickstarter was a notable and fast-paced vehicle for a project to streamline a way to accrue funds. 

For this project, I scraped data from [webrobots](https://webrobots.io/kickstarter-datasets/).

Data was gathered and cleaned so that it could be used for visualizations and machine learning models.

## The Data

Here are the original columns that came from the scraped data. While this does give us a lot of information on projects from 2009 until 2021, there were things that I had to drop, clean, or change completely in order for the data to give meaningful information.

```
Index(['backers_count', 'blurb', 'category', 'converted_pledged_amount',
       'country', 'country_displayable_name', 'created_at', 'creator',
       'currency', 'currency_symbol', 'currency_trailing_code',
       'current_currency', 'deadline', 'disable_communication', 'friends',
       'fx_rate', 'goal', 'id', 'is_backing', 'is_starrable', 'is_starred',
       'launched_at', 'location', 'name', 'permissions', 'photo', 'pledged',
       'profile', 'slug', 'source_url', 'spotlight', 'staff_pick', 'state',
       'state_changed_at', 'static_usd_rate', 'urls', 'usd_pledged',
       'usd_type'],
      dtype='object')
```

Cleaning data is where most time is usually spent, to clean one has to understand the data and the relation keeping it all together.

One of the many obstacles I faced when looking at the data was with a column named "category"; within that column, there were 158 unique categories.

This seemed a bit messy if I were to visualize category counts.

So after a little research, I added a new column called "main_category" to the dataset. It is made up of 15 possible categories that contain the 158 original categories. 

Every sub-category now had a home in the main category and this new column could be better visualized.

```
df.category.value_counts()

Comedy            9723
Web               8820
Product Design    4000
Spaces            3774
Tabletop Games    3633
                  ... 
Quilts             100
Chiptune            56
Games               55
Kids                20
Video Art            7
Name: category, Length: 158
```

```
df.main_category.unique()

array(['crafts', 'food', 'tech', 'publishing', 
			'theater', 'design', 'music', 'art', 
			'games', 'photography', 'film & video', 
			'fashion','comics', 'dance', 'journalism'], 
			dtype=object)
```

## Kickstarter Main Categories

Kickstarter Projects in all catgories from 2009-2020
![cats](/assets/images/proj_cat.png)

Treemaps and Sunburst charts are visualizations that help to show relationships within data. Both of these graphs illustrate the relation in size of each sub category within their main category.

<img align="right" width="100" height="100" src="/assets/images/vvtrmd.gif">

<img align="right" width="100" height="100" src="/assets/images/sunburst.gif">


## Success and Failure

Delving further into the data, we can see that within each sub-category, there is still another way to split the projects. We can look at which projects were successful and which failed to reach their goals.

![](/assets/images/pie_purp.png)

![](/assets/images/mainsuccfail.png)


## Time and Projects

Now then, what are these projects asking for from backers? MONEY.

$5,000 and $10,000 were the most popularly monetary goals for projects. Followed by $1,000, $2,000, and$3,000. Most of these goals could be reached fairly quickly with enough backers.

The sooner the pledge is over, the sooner the project could get underway and deliver what was promised to backers as well as go to market as a product.

40% of projects have a deadline of 30 days to complete their funding goal. However, a project reaching its monetary goal does not ensure that the project will fulfill its promises. Projects have had to refund pledged money for not coming through with promises made.

![](/assets/images/dur_days.png)


Kickstarter has gained popularity over the years. The spread of Covid-19 in 2020 has sparked more interest in projects being launched and subsequently acquiring backers and reaching their goal. This is something that can be done entirely online and allows for backers to feel like they are part of a community, doing good for others or making themselves useful. 

![](/assets/images/yearlaun.png)


## Predictions

Time to apply machine learning to the data.

After a little encoding, it is time for splitsville. The data is divided into a training set and a testing set, in the usual 80:20 split.

For this classification problem, I went with Random Forest, Logistic Regression, and an XGBoost to see which would give me the best accuracy scores.

**Scores on testing data:**

Random Forest: 0.7761014171406536

Logistic Regression: 0.6619343389529725

XGBoost: 0.7360026619343389


The Random Forest model has the best score, now let's try to pump it up.

After some hyperparameter tuning, I was able to get the best parameters for the model on the training data.


```
rfc best params: {'max_depth': 22, 'n_estimators': 1000, 'n_jobs': -1}
rfc scores: 0.7837684885154027
```


Performance on test data:

```
rfc accuracy score 0.7894853593611357
```

I found the Kickstarter data to be highly intriguing, I love to see data that has been compiled over several years. Trends and history are stored in that type of data and it takes a good visual artist to be able to extract the story within.


