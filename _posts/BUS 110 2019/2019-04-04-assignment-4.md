---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: A4 - Building Your Personal Brand, due Thurs, Apr 25

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   **Assigned** Thurs, Apr. 4, 2019; **Due:** Thurs, Apr. 25 @ 23:59 PM via [submission portal](https://forms.gle/QNcuW8p7946SsJfj8); Handout: [PDF](https://drive.google.com/file/d/1xd50nfZ2EJW4dMQV7Wj9Vxnv0KwR74PF/view?usp=sharing)

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
categories: [BUS 110]
tags: []
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

**Overview**: In this assignment, you will write your own resume and build your online portfolio

## Resume Requirements
Your resume must have at least the following sections:
1. Your name
2. Your contact information
3. An objective statement (what are you looking for in a job?)
4. The languages (computer or speaking) you know
5. A summary of your education
6. A summary of your experience 
7. Any awards and/or honors

A **sample** is provided as a class-handout: [Gracie Hopper resume](https://drive.google.com/file/d/1ojFrdyhXyLPeVTv5X6rZkpUgl84GvUbk/view?usp=sharing)

## Online Portfolio
In `HTML`, create a website that includes:
1. Your name and personal logo
2. Your objective statement
3. *At least* **five** portfolio items (e.g., drawings, music samples, poems, programs)
4. A link to your resume
5. Links to your relevant social media profiles (e.g., Twitter, LinkedIn)

## Submission Portal
Submit this assignment here: [https://forms.gle/QNcuW8p7946SsJfj8](https://forms.gle/QNcuW8p7946SsJfj8)

## Example

Check out this example in repl.it: [https://ramnauthportfolio--rramnauth2220.repl.co/](https://ramnauthportfolio--rramnauth2220.repl.co/)

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Rebecca Ramnauth</title>
    <link rel="icon" href="https://static.thenounproject.com/png/15612-200.png">
    <link href="https://fonts.googleapis.com/css?family=Major+Mono+Display|Roboto+Mono" rel="stylesheet">

    <style>
      body {
        font-family: 'Roboto Mono', monospace;
        padding: 50px;
      }
      h1 {
        font-family: 'Major Mono Display', monospace;
        font-size: 50px;
        margin: 0px;
      }
      h2 {
        font-family: 'Roboto Mono', monospace;
        font-size: 20px;
      }
      .skill {
        background-color: #000000;
        color: #ffffff;
        font-family: 'Roboto Mono', monospace;
        padding: 10px;
        margin-right: 10px;
        display: inline-block;
      }
      .gallery {
        height: 150px;
        margin: 25px;
        background-color: yellow;
      }
      .gallery:hover {
        background-color: red;
      }
      div {
        margin: 20px;
      }
      .abstract {
        padding: 30px;
        background-color: black;
        color: white;
      }
      a {
        background-color: yellow;
        color: black;
        padding: 10px;
        text-decoration: none;
        display: inline-block;
        border-radius: 5px;
      }
      a:hover {
        background-color: red;
      }
      .social {
        height: 30px;
        display: inline-block;
      }
    </style>
  </head>
  <body>
    <h1> Rebecca Ramnauth </h1>
    <h2> Software Developer, Professor, and Eternal Student </h2>
    <p class="skill"> HTML, CSS, JS </p>
    <p class="skill"> Python </p>
    <p class="skill"> Lisp/Scheme </p>
    <p class="skill"> C/C++ </p>
    <p class="skill"> Haskell </p>
    <p class="skill"> VBA </p>

    <div class="abstract">
      <h1> Abstract </h1>
      <img class="gallery" src="https://github.com/rramnauth2220/rramnauth2220.github.io/blob/master/images/proj1.png?raw=true"/>
      <img class="gallery" src="https://github.com/rramnauth2220/rramnauth2220.github.io/blob/master/images/proj2.png?raw=true"/>
      <img class="gallery" src="https://github.com/rramnauth2220/rramnauth2220.github.io/blob/master/images/proj3.png?raw=true"/>
      <img class="gallery" src="https://github.com/rramnauth2220/rramnauth2220.github.io/blob/master/images/proj4.png?raw=true"/>
      <img class="gallery" src="https://github.com/rramnauth2220/rramnauth2220.github.io/blob/master/images/proj5.png?raw=true"/>
      <img class="gallery" src="https://github.com/rramnauth2220/rramnauth2220.github.io/blob/master/images/proj6.png?raw=true"/>
    </div>

    <div>
      <h1> Art </h1>
      <img src="drawings.JPG"/>
    </div>

    <div class="abstract">
      <h1> Animations </h1>
      <h2> <a href="https://rramnauth2220.github.io/wave/"> Waves</a>: Music-based animations </h2>
      <h2> <a href="https://rramnauth2220.github.io/explore/"> FINN</a>: Sentiment-based animations </h2>
    </div>

    <div>
      <h1>Address</h1>
      <p> Link your <strong> own </strong> resume and media here.</p>
      <h2> <a href="https://drive.google.com/file/d/1ojFrdyhXyLPeVTv5X6rZkpUgl84GvUbk/view?usp=sharing" target="_blank"> Resume</a>: Gracie Hopper Example </h2>
      <a href="https://twitter.com/ghc?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor">  <img class="social" src="https://image.flaticon.com/icons/svg/23/23931.svg"/> </a>
      <a href="https://www.facebook.com/gracehoppercelebration/">  <img class="social" src="https://image.flaticon.com/icons/png/512/69/69407.png"/> </a>
      <a href="https://www.instagram.com/explore/locations/426711461/grace-hopper-celebration-of-women-in-computing/?hl=da">  <img class="social" src="https://cdn3.iconfinder.com/data/icons/transparent-on-dark-grey/500/icon-04-512.png"/> </a>
    </div>
    
  </body>
</html>
```