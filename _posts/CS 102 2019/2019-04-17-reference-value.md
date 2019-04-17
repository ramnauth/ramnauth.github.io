---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Reference Versus Value

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   What is the difference between reference and value? How can we 'pass by reference' versus 'pass by value'?

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

```cpp
#include <iostream> 
 
using namespace std; 
 
// CALL BY VALUE is the default way of passing parameters 
// in C/C++: the parameter is a COPY of the original, so 
// the function can't change the original. 
int changeByValue(int x, int amount); 
 
// CALL BY REFERENCE is indicated by the (&) after the type 
// of the parameter. It means the parameter is initialized 
// as a reference (aka a pointer) to the original value,  
// so it can change the original. 
int changeByRef(int& x, int amount); 
 
int main(){   
    int x = 10; 
    changeByValue(x, 23);   
    cout << "x = " << x; 
    changeByRef(x, 23); 
    cout << "x = " << x; 
    return 0; 
} 
 
int changeByValue(int x, int amount) {
    x = x + amount;   
    return x; 
} 
 
int changeByRef(int& x, int amount) {   
    x = x + amount;   
    return x; 
} 
```

An illustration by [Mathwarehouse](https://www.google.com/url?sa=i&source=images&cd=&cad=rja&uact=8&ved=2ahUKEwjX2ujDldfhAhWnnuAKHRnxB7gQjRx6BAgBEAQ&url=https%3A%2F%2Fwww.mathwarehouse.com%2Fprogramming%2Fpassing-by-value-vs-by-reference-visual-explanation.php&psig=AOvVaw2uKT8KMQlgWiTqhZDVKb-a&ust=1555591510322839): 

![Gif Reference v Value](https://www.mathwarehouse.com/programming/images/pass-by-reference-vs-pass-by-value-animation.gif)