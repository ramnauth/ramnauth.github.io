---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Algorithms

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   What is an algorithm and why are algorithms important? 

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
categories: [CS 101]
tags: []
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

**[Definition:](https://liucs.net/cs101f18/n5-algos.html)** an algorithm is a *finite* *sequence* of *unambiguous* and effectively *computable* instructions that produce some intended *result*.

Let’s explore some of those terms in more detail:

- **finite:** an algorithm must terminate at some point. If it might go on forever, then we might never achieve the intended result.
- **sequence:** the steps are ordered (first do this, then do that, etc.) and the order (in most cases) must be followed to achieve the correct result.
- **unambiguous:** each step must be clear. There can be no confusion as to what must be done. If multiple interpretations of the instruction are possible, it’s not an algorithm.
- **computable:** each step must specify some task that can be performed. This gets a little theoretical, 
but there are some types of problems that no computer can solve in finite time. For now, let’s try to “predict tonight’s lottery numbers.” Because the lottery is random, there’s no algorithm we can create/follow to reliably predict it.
- **result:** we develop an algorithm to reach an answer/output/end state, or else, what's the point?

## TBC 