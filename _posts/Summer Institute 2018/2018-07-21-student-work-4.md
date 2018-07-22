---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Student Work - Poisonous Plants

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   As an introduction to programming, this group from the 2018 Summer Honors Institute @ LIU developed an educational game that demonstrates their passion for and awareness of the environment. 


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

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSW3PHRxyr5vdidi0pGzPe5ttR2HyoSme_F9OU5MF_mj9H0bzzucfAhNTqJzvfj7TcrVmr3GcZh0pYf/embed?start=false&loop=false&delayms=3000" frameborder="0" width="480" height="299" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<iframe allowtransparency="true" width="485" height="402" src="//scratch.mit.edu/projects/embed/236744337/?autostart=false" frameborder="0" allowfullscreen></iframe>

## Love what you see?

Check out their code on [Scratch](https://scratch.mit.edu/projects/236744337/) and [GitHub](https://github.com/angelatom/Oppenheimer_Disciples).

```java
// 0: Init State
// 1: Game State
// 2: Game-over State

int gameState = 0; // start at init state
PImage start; // storage of the start image
int round = 1; // Game should start at round 1
// Plant images vars
Plants plants; 
PImage one, two, three;
int posOne, posTwo, posThree;
// Win boolean
boolean win = false;

// During setup, some of the variables are initialized
void setup() {
  size(1024, 768);
  //fullScreen();
  start = loadImage("start.jpg");
  plants = new Plants();
... //see all source code on GitHub
```