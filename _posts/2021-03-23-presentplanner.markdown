---
layout: post
title:      "PresentPlanner"
date:       2021-03-23 23:05:22 +0000
permalink:  presentplanner
---


For the second module project in the Flatiron School curriculum, I was tasked with creating a Sinatra application to render a basic Ruby app in the user’s browser. My goal is always to create something that I would actually use. One of my biggest social shortcomings is my forgetfulness. When is my friend’s birthday? Which sweater did my wife say she liked last month?

The app I decided to make, PresentPlanner, is designed to help with those moments where panic sets in when you’re struggling to figure out what gift to buy someone last minute. By allowing users to create gift lists for various recipients in their lives, they can keep track of ideas that come to them throughout the year so they can remember the perfect present for their friends and family.

Here are the project requirements set by Flatiron School:

* Build an MVC Sinatra application.
* Use ActiveRecord with Sinatra.
* Use multiple models.
* Use at least one has_many relationship on a User model and one belongs_to relationship on another model.
* Must have user accounts — users must be able to sign up, sign in, and sign out.
* Validate uniqueness of user login attribute (username or email).
* Once logged in, a user must have the ability to create, read, update and destroy the resource that belongs_to user.
* Ensure that users can edit and delete only their own resources — not resources created by other users.
* Validate user input so bad data cannot be persisted to the database.

With the specs in mind, I began creating the plan and framework for the app. I decided on four models:

* User
* Recipient
* List
* Gift

Each model would be able to Create, Read, Update, and Delete (CRUD) from the SQLite database using ActiveRecord. Using the MVC framework, I developed a structure that allowed interactions between the models and programmatically updated the views that are displayed to the user based on the data that had (or hadn’t been) added to the database.

Once I got the basic structure and functionality in line, I waded into unfamiliar waters: front-end HTML, CSS, and Javascript frameworks. I opted for the Bootstrap framework to make my app a lot prettier and more user friendly.
By using the Bootstrap tools, PresentPlanner went from this:

![](https://miro.medium.com/max/1400/1*34OEt3Z9kXekZprAtvI3jw.png)


To this:

![](https://miro.medium.com/max/1400/1*xQjj6akfyCHKFq-GNuf4_A.png)

This project also allowed me to play with a whole lot of forms. The biggest challenge for me was creating the correct complex relations while making the forms user friendly and nice to look at. Here’s the HTML/ERB for the Create New List Form:

<script src="https://gist.github.com/wtwerner/750293c26d0c163e9d5fa831845dfa4e.js"></script>

Which renders in the browser as:

![](https://miro.medium.com/max/1400/1*-dFRkTw_XCoDvcBhgFanvg.png)


This form displays a couple fun concepts: Container formatting with Bootstrap, programmatically iterated options for the recipient selection.

Even though there are still a lot of feature and stylistic upgrades I plan to make, this was an extremely fun and rewarding project. Best of all, I made an app I’ll actually use!
