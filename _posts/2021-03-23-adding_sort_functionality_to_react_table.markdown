---
layout: post
title:      "Adding Sort Functionality to React Table"
date:       2021-03-24 02:51:37 +0000
permalink:  adding_sort_functionality_to_react_table
---


I recently created a React app that made it convenient to search for and catalog board games. For each of the collection pages, owned games and wishlist, there is a static table that displays a list of games. In order to improve the ability to find games, I wanted to add sorting functionality to the tables so the user can more easily find a desired game.

Here is the JSX that renders the basic table:

<script src="https://gist.github.com/wtwerner/41ffeb14f2992dc0589b1c969776883f.js"></script>

Since each table row is rendered by mapping through the local state of the component, all I need to do is modify the state and React will notice the change and re-render the table rows to match the new state order.

This is what the state in my component looks like:

<script src="https://gist.github.com/wtwerner/3d4d5ecb1e29b72e2a927c9d84f6b5ad.js"></script>

Since I used Redux to manage my global state, I am pulling the games initially from that and setting `sorted` to initialize as `false`. The next thing I need to do is create the function that actually does the heavy lifting of sorting the games.

An important thing to consider is that the Javascript `.sort()` function is destructive, meaning that it will overwrite the initial array that it is sorting. With that in mind, I need to persist the unsorted array for when I want to revert the table back to the unsorted state. I do this by creating a new constant const ` unsorted = […this.props.userGames]`.

Next, I need to tackle the ordering and disordering. For sorting, I am using the Javascript .sort() function, which acts on an array to compare the items and return the reordered array. This reordered array is then used to set the new local state. For the disordered array, I simply need to set the state to the unsorted constant we assigned earlier.

This is the finished function (in this case, I am sorting by the game rank):

<script src="https://gist.github.com/wtwerner/0a953c5f9aecf2b1da5ff98ce61f61c2.js"></script>

Finally, I need to create a button that I can use to invoke my new sorting function:

<script src="https://gist.github.com/wtwerner/775e6ff6a5acd0eeaab7857211ce876c.js"></script>

And that should do it! Here is the button in action:

![](https://miro.medium.com/max/1400/1*s_J8q2aVhjkmbCVV9WHsiA.gif)

I hope this helps anyone trying to do something similar.
