---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: A2 - Base Converter - Solutions

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Example solutions for [Assignment 2 - Base Converter](https://ramnauth.github.io/cs%20102/2018/09/19/homework-2/)

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
tags: [C++, Assignments]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

**Variations**

- [A solution](https://ramnauth.github.io/cs%20102/2018/09/19/homework-2-solution/#variation-1) written only in the `main` function
- [A solution](https://ramnauth.github.io/cs%20102/2018/09/19/homework-2-solution/#variation-2) that is *modularized* (uses functions to perform separate tasks) and uses recursion


### Variation 1

```cpp
// Rebecca Ramnauth

#include <iostream>
#include <string>

using namespace std;

int main(){
    cout << "-------------------------------" << endl;
    cout << " Base 10 --> Base X Converter  " << endl;
    cout << "-------------------------------" << endl;

    string base, val; 
    cout << "Value to convert: ";
    getline(cin, val);
    cout << "Base to convert " << val << " into: ";
    getline(cin, base);

    string ans = "";

    int intVal = stoi(val);
    int intBase = stoi(base);
    while (intVal > 0) {
        cout << intVal << "/" << intBase << " = " << intVal/intBase << " with remainder of " << intVal%intBase << endl;
        ans = to_string(intVal%intBase) + " " + ans;
        intVal = intVal/intBase;
    }
	
    cout << "Answer: " << ans << endl; 
	
	return 0;
}
```

```cpp
SAMPLE OUTPUT

>	Value to convert: 7
>	Base to convert 7 into: 2
>	7/2 = 3 with remainder of 1
>	3/2 = 1 with remainder of 1
>	1/2 = 0 with remainder of 1
>	Answer: 1 1 1
```

### Variation 2

```cpp
// Rebecca Ramnauth

#include <iostream>
#include <string>

using namespace std;

void collectInputs();
void isConfirmed(int val, int base);
bool isValid(int val, int base);
void convertBase(int val, int base);

int main(){
    collectInputs();
	return 0;
}

/* collect console inputs for value and base*/
void collectInputs(){
    string base, val; 
    cout << "Value to convert: ";
    getline(cin, val);
    cout << "Base to convert " << val << " into: ";
    getline(cin, base);

    int intVal = stoi(val); // stoi converts a string into an int
    int intBase = stoi(base);

    bool moveOn = isValid(intVal, intBase);
    if (moveOn)
        isConfirmed(intVal, intBase);
}

/* check if user input is valid */
bool isValid(int val, int base){
    // check if val is a legal value i.e. integer and positive
    // check if base is a legal value i.e. integer and positive
    if (val >= 0 && base >= 1)
        return true;
    else {
        cout << "Invalid inputs. Try again." << endl;
        collectInputs();
        return false;
    }
}

/* ask for user confirmation before computing*/
void isConfirmed(int val, int base){
    string confirmed;
    cout << "Confirm: convert " << val << " in base 10 into base " << base << " (Y/N)? ";
    getline(cin, confirmed);

    if (confirmed.find('N') != -1){
        collectInputs();
    }
    else {
        convertBase(val, base);
    }
}

// recursive implementation
void convertBase(int val, int base){
    /*
        1. Divide the number by the base
        2. Store the remainder
        3. Repeat the process with the whole number part of division
        4. Stop when you reach zero
        5. Answer = remainders in reverse order
    */
   if (val > 0){
        int wholeDivide = val/base;
        cout << val << " / " << base << " = " << wholeDivide << ", remainder " << val % base << endl;
        convertBase(wholeDivide, base);
   }

   cout << val % base;
}
```

```cpp
SAMPLE OUTPUT

>	Value to convert: 7
>	Base to convert 7 into: 2
>	Confirm: convert 7 in base 10 into base 2 (Y/N)? Y
> 	7 / 2 = 3, remainder 1
>	3 / 2 = 1, remainder 1
>	1 / 2 = 0, remainder 1
>	0111
```