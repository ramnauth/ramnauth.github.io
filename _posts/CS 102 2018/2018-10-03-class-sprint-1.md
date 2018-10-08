---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Number Type

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Example solution for the classroom coding exercise: `numberType()`

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
categories: [CS 102, Coding Challenges]
tags: [C++]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

**Prompt**: your program should 
1. ask the user for an integer
2. say whether the number is positive, negative, or zero.

### Solution

**Note**: In the real world, there are many ways to do or say something. This also applies in programming. There is never *one* solution. Here's just one of the many solutions to this coding challenge.

```cpp
#include <iostream>

using namespace std;

void numberType(); // a prototype to let the compiler know that this function exists

int main(){
    numberType();
    return 0;
}

int enterNumber(){ // this function is only responsible for storing and returning the value of cin
    int num = 0; // defined as 0
    cout << "Enter a number: ";
    cin >> num;
    return num;
}

void numberType(){
    int num = enterNumber();
    if (num > 0)
        cout << "The number " << num << " is positive" << endl;
    else if (num < 0)
        cout << "The number " << num << " is negative" << endl;
    else
        cout << "The number " << num << " is zero" << endl;
}
```
