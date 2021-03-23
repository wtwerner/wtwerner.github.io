---
layout: post
title:      "Using Javascript to Make Multiple Views for a SPA"
date:       2021-03-23 23:11:43 +0000
permalink:  using_javascript_to_make_multiple_views_for_a_spa
---


I was recently tasked with creating a Single Page Application (SPA) for Flatiron School. The requirements were simple enough, use a Rails API backend and a Javascript/HTML/CSS frontend to make a CRUD application that has several fetch requests from the frontend. I decided to stick with my usual plan: make something that I would actually use.

![](https://miro.medium.com/max/1400/1*-KYp4DVM2w7704vZ-yxgqw.png)

I began work on my movie watchlist application, WatchNext, and quickly realized that I wouldn’t be able to keep all the information on one view as I had originally intended. Instead, I would need to split up the Watchlist, Search, and Watched views using HTML and Javascript.

The solution I arrived at was to create a div for each view in the index file for my application.

<script src="https://gist.github.com/wtwerner/98defa3189f10dc337e28f976c52c520.js"></script>

In that snippet, you can see that the views for Search and Watched are both hidden by default. This is because I wanted my Watchlist view to be the default upon page load. I further reinforced this by including the following Javascript at the end of my index file to trigger the initial page function.

<script src="https://gist.github.com/wtwerner/05346e3b85d7a650697c0da2c7b18856.js"></script>

The real magic happens with the navigation bar buttons at the top of the page. I created links for each of the three views and attached the following listeners to each.

<script src="https://gist.github.com/wtwerner/6d44307760c51e1ce580761146582a93.js"></script>

As you can see, I simply adjust the div class for each to be hidden or not in order to display the desired view. Each of the views still exist within the document, but are hidden from view when not required. This is a simple way to allow for multiple views while keeping everything within a single page.
