---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: C++ Review Sheet

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   C++ review sheet, updated as of 9/10/2018

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
tags: [C++, Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
This review sheet will cover the following topics:

1. [Basics](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-I/#basics) - Zybook Chapter 1
2. [Data Types](https://ramnauth.github.io/cs%20102/2018/09/11/cpp-I/#data-types) - Zybook Chapter 2

## Basics

```cpp
//This is a comment

/*
    This is a multiline comment
*/

#include <iostream>

using namespace std;
int main() {
    cout << "Hello World!" << endl;
	return 0;
}
```

## Data Types

```cpp
#include <iostream>

using namespace std;
int main() {

    // int is an integer value: 0, 1, 2, 3, ...
    int myAge = 35;
    // const values cannot be changed
    const double PI = 3.14;
    // char is a letter denoted in single quotes: 'a', 'b', 'c', ...
    char myGrade = 'A';
    // bool is either true (1) or false (0)
    bool isHappy = true;
    // float are numbers with max 7 sig figs
    float favFloat = 3.141592;
    // double has 2x precision of a float, max 16 sig figs
    double favDouble = 3.312141592341213;
    
    cout << "Printing the number " << PI << endl;

    /* Other types include:
         short int: >= 16 bits
         long int: >= 32 bits
         long long int: >= 64 bits;
         unsigned int: same size as signed int
         long double >= double
    */

    cout << "Size of int: " << sizeof(myAge) << " bytes." << endl;
    cout << "Size of double: " << sizeof(favDouble) << " bytes." << endl;
    cout << "Size of float: " << sizeof(favFloat) << " bytes." << endl;
    cout << "Size of bool: " << sizeof(isHappy) << " bytes." << endl;
    cout << "Size of char: " << sizeof(myGrade) << " bytes." << endl;
    
    int largestInt = 2147483647;
    cout << "Largest int possible: " << largestInt << endl;
   
    int smallestInt = 2147483648; // also equal to -2147483648
    cout << "Smallest int possible: " << smallestInt << endl;
	
	return 0;
}
```