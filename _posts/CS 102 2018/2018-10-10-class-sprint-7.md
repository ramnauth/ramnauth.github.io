---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Printing ASCII Value

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Example solutions for the `getASCII()` classroom coding exercise

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

**Variations**

- [A solution](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/10/class-sprint-7/#variation-1) entirely in `main`
- [A solution](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/10/class-sprint-7/#variation-2) partially in `main`
- [A solution](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/10/class-sprint-7/#variation-3) *modularized* outside of `main`

### Variation 1

```cpp
#include <iostream>

using namespace std;

int main(){
    char c;
    cout << "Enter a symbol: ";
    cin >> c;
    cout << "The ASCII value is " << (int)c;
    return 0;
}
```

```cpp
SAMPLE OUTPUT

>	Enter a symbol: R
>	The ASCII value is 82
```

### Variation 2

```cpp
#include <iostream>

using namespace std;

int getASCII(char sym); // just returns the ASCII value

int main(){
    char c;
    cout << "Enter a symbol: ";
    cin >> c;
    cout << "The ASCII value is " << getASCII(c);
    return 0;
}

int getASCII(char sym) {
    return (int)sym;
}
```

```cpp
SAMPLE OUTPUT

>	Enter a symbol: R
>	The ASCII value is 82
```

### Variation 3

```cpp
#include <iostream>

using namespace std;

char enterSymbol(); // handles input of a symbol
int getASCII(char sym); // just returns the ASCII value

int main(){
    cout << "The ASCII value is " << getASCII(enterSymbol());
    return 0;
}

char enterSymbol() {
	char c;
    cout << "Enter a symbol: ";
    cin >> c;
	return c;
}

int getASCII(char sym) {
    return (int)sym;
}
```

```cpp
SAMPLE OUTPUT

>	Enter a symbol: R
>	The ASCII value is 82
```