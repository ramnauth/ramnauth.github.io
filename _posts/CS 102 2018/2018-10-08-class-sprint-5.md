---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Prof. League's Quiz 4

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
tags: [C++, Coding Challenges]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
You may download and complete the following quiz. The solutions are posted below.
<iframe src="https://drive.google.com/file/d/1_TU7Ed6hRaY5-3owg6zErfiaGmzNOLoM/preview" width="720" height="240"></iframe>

## Solutions

### Question 1
The following program fragment uses loops. What is the output? 
```cpp
int i = 0;
int n = 0;
while (i <= 4) {
	i = i + 1;
	n = n + i;
	cout << n << "\n";
}
```
**Solution:**
```cpp
1
2
3 
4 
5 
15
```

### Question 2
The following program fragment uses loops. What is the output? 
```cpp
int a = 8; 
while (a > 0) {
	cout << a << "\n";
	a /= 2;
}
```
**Solution:**
```cpp
8
4
2
1
```

### Question 3
The following program fragment uses loops. What is the output? 
```cpp
int p = 1;
for (int i = 1; i <= 10; i++) {
	if (i % 3 == 0) {
		p += i;
	}
}
cout << p << "\n";
```
**Solution:** `19`

### Question 4
The following program fragment uses loops. What is the output? 
```cpp
for (int i = 2; i <= 4; i++) {
	for (int j = 2; j < 4; j++) {
		cout << i * j << " ";
	}
	cout << "\n";
}
```
**Solution:**
```cpp
4 6
6 9
8 12
```