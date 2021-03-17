---
layout: post
title:      "Creating my first CLI Gem"
date:       2021-03-17 19:16:40 +0000
permalink:  creating_my_first_cli_gem
---


For the past several months, I’ve been enrolled in the part-time online software engineering curriculum at the Flatiron School. My cohort and I have been learning the basics of coding with the Ruby language. For our first major project, we were given the task of creating our own simple Ruby CLI (command line interface) application. Basically, we were asked to create a service that would collect information from a user and display information in the CLI that is pulled from an external data source.

In deciding what I would create, I wanted to make something that I would actually use. My first ideas were around NASA launch schedules, the weather, or even getting information about the video game, Animal Crossing. Each of those elicited a polite, “yeah, I guess that’s interesting” from my wife. The idea I finally landed on is one we could use together.

My wife and I share a deep interest in movies and most date nights, especially during the current age of social distancing and lockdowns, include watching a movie together. The problem that I decided to solve was how much time and energy we put into deciding what to watch. What we needed was a simple application to take some basic information around the criteria we were looking for in a movie and giving us a randomized list of options to choose from in order to make picking something out a lot easier than parsing through hundreds of options.

I was able to find an extremely comprehensive API to grab data from at TMDb (The Movie Database), which would be perfect for this application. In order to plan for the project, I had to first decide on some basic guidelines surrounding what I want the result to be and the necessary information required from the user to achieve that result. In defining this, I was able to make a flowchart to help clarify the project’s structure.

Then the hard work began. Using the knowledge I’d gathered from the courses at Flatiron and supplemented with a good amount of Googling, I was able to start writing code. My first main roadblock came when I had to learn how to get, store, and access data from the TMDb API, but once I got through that, things came together relatively quickly.

I definitely made some rookie mistakes along the way. I found myself creating unnecessary classes and methods, forgetting basics like iterating through hashes, and even accidentally exposing my TMDb API key on Github. But those mistakes definitely taught me a whole lot more about writing Ruby code than if I hadn’t made them.
In the end, I created a simple app that I’m proud of and even more importantly, one my wife is actually excited to use during our next movie night.
