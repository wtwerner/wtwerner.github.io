---
layout: post
title:      "Adding Login/Logout/Signup to a Navbar with React and Redux"
date:       2021-03-23 23:14:29 +0000
permalink:  adding_login_logout_signup_to_a_navbar_with_react_and_redux
---


Recently, I was building my final Flatiron School portfolio project, BG Logger, and I wanted to add a responsive Navbar that had responsive buttons that had buttons for login, logout, and signup. I wanted these to be rendered appropriately if there was a current user. Since I was using Redux to manage my centralized state, I would need to connect my Navbar component to the store in order to monitor the current user status.

Prior to adding the buttons, my Navbar was rendering a simple, responsive component that had links to the various routes of the application.

<script src="https://gist.github.com/wtwerner/d8c366036a5e27feb9e3c46dc225669a.js"></script>

In order to render the buttons, I had to add a Bootstrap Form that programmatically renders the appropriate buttons. I can do that by calling a function within the JSX.

<script src="https://gist.github.com/wtwerner/88e85bacbcb4ea4b9a14d3f43b94f354.js"></script>

This function would need to check if there’s a current user and render a logout button if there is one and render login/signup assuming there is not a current user. But before that, this component would need to be able to see the Redux store and access the current user from state. The first step is to import connect so that I can make the Navbar a connected component.

<script src="https://gist.github.com/wtwerner/0a17822b3981b9296cb3310d629890b0.js"></script>

From there, I need to connect the component to Redux and create a mapStateToProps function so I can access the required state data from the component itself. I also inject the logout action so I can use that function on my logout button rather than redirecting to a separate page.

<script src="https://gist.github.com/wtwerner/cfb48ddc9c93849a461dfa1c5a1958fd.js"></script>

Now, I have all the ingredients necessary for the functionality I’m looking to add. This is what the final code looks like:

<script src="https://gist.github.com/wtwerner/cc4ae146db4edca056becdf2c67f0355.js"></script>

Since it’s a functional component, I used hooks in order to access the current user and the logout function within the component. This is a pretty simple way to add some nice functionality to your React Navbar.

![](https://miro.medium.com/max/1400/1*f5MjYNVGB5ahlXuTt6xJkQ.gif)
