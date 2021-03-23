---
layout: post
title:      "The Importance of Proper Planning"
date:       2021-03-23 23:09:32 +0000
permalink:  the_importance_of_proper_planning
---


I just finished a new Rails app for my Flatiron School portfolio. Here’s a quick walkthrough of the finished (but not “finished”) product:

<iframe width="560" height="315" src="https://www.youtube.com/embed/KBAYhbkEDSI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

As you can see, it doesn’t have the normal level of polish that my projects would normally have. That’s because of a big issue: I didn’t plan well enough before starting!

Namely, I didn’t plan my data structure well enough. Upon creating a Rails app, the first thing you must consider is what objects you are going to need and how each will associate with each other through database associations. On the first day of work on my project, I sat in a car dealership waiting for some repairs with a big legal pad and a pen. I considered my app, the features I wanted it to have, and the requirements of the project. The requirements that should have steered me in the right direction are:

* At least two has_many_through relationships
* At least one many-to-many relationship
* The join table of the many-to-many relationship must include at least one user submittable attribute

These are important because it means that I need a join table and that join table must have more than just a couple foreign keys to associate the two records it’s relating. Here’s the original association I came up with:

```
User
  has_many :meals
  has_many :ingredients
Meal
  belongs_to :user
  has_many :meal_ingredients
  has_many :ingredients, through: :meal_ingredients
Ingredient
  belongs_to :user
  has_many :meal_ingredients
  has_many :meals, through: :meal_ingredients
```
	
The thought was that I would have a simple app to log meals based on the ingredient category as a lightweight way to track and visualize how much of each food group my daughter was eating. For the purposes of this project though, it created a whole lot of headaches surrounding:

> “The join table of the many-to-many relationship must include at least one user submittable attribute”

What would I even put in the join table? I couldn’t think of anything so I abandoned that structure, started an entirely new app, but with days wasted and no real work to show for it.

Here’s the kicker, I went through this same cycle two more times. I found myself hitting a limitation with associations or struggling to complicate the app enough to meet the requirements. It took hours of talking it through to myself before finally landing on this structure:

![](https://miro.medium.com/max/1400/1*WDXEZ7q4TW2k1m5h4VmK1Q.png)

This made the project sufficiently complicated with two join tables comments and recipe_categories. I was able to satisfy that pesky requirement of allowing a user to submit information to the join table in the form of @comment.content.

I learned a ton during this project, but the most important lesson was to take that extra hour or two when defining the framework of your application. Otherwise, you may find yourself in the position I did.
