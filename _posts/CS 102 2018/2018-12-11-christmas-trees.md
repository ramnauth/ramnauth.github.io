---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Christmas Trees

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   

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
categories: [CS 102]
tags: [C++]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

Write a program that generates a Christmas tree.

## Triangular Trees
Generate a triangular tree given user-inputted number of levels.
```cpp
Enter a number (levels): 6
     ^
    ^^^
   ^^^^^
  ^^^^^^^
 ^^^^^^^^^
^^^^^^^^^^^
```

## Layered Trees
Generate a layered tree given user-inputted number of layers and layer's depth.
```cpp
Enter a number (layers): 5
Enter a number (depth of each layer): 3
              ^
             ^^^
            ^^^^^
             ^^^
            ^^^^^
           ^^^^^^^
            ^^^^^
           ^^^^^^^
          ^^^^^^^^^
           ^^^^^^^
          ^^^^^^^^^
         ^^^^^^^^^^^
          ^^^^^^^^^
         ^^^^^^^^^^^
        ^^^^^^^^^^^^^
```

## Decorated Trees
Simulate a tree with twinkling lights and/or ornaments using thread sleeping.
```
code coming soon
```