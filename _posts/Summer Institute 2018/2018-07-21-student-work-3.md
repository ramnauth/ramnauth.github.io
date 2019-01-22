---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: SI 2018 - Health Catch

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   As an introduction to programming, this group from the 2018 Summer Honors Institute @ LIU developed a game to encourage healthy eating.


# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [Summer Institute, Student Work]
tags: [Scratch, Processing, Java]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vQQPyCJbRo1sxGaiUJ5WxURLNphFq6UC2fnMWK-XHIhv-qc92OoYqz4naFzolucencHWJYwsO5k6w9J/embed?start=false&loop=false&delayms=3000" frameborder="0" width="480" height="299" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<iframe allowtransparency="true" width="485" height="402" src="//scratch.mit.edu/projects/embed/236643230/?autostart=false" frameborder="0" allowfullscreen></iframe>
    
## Love what you see?

Check out their code on [Scratch](https://scratch.mit.edu/projects/236643230/) and [Github](https://github.com/DanielGelfand/HealthCatch).

```java
PImage basket;
PImage vegetable;
PImage cheesePuff;
int score= 0;

//Instantiate objects
Bowl catcher = new Bowl();
Healthy kale = new Healthy();
Bad puff = new Bad();


//Initial setup
void setup(){
  size(600,600);
  basket = loadImage("basket.png");
  vegetable = loadImage("Kale.png");
  cheesePuff = loadImage("cheesePuff.png");
}

//Displays and runs the game
void draw(){

... //see all source code on GitHub
```