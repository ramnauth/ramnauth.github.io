---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Prof. League's Quiz 3

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
<iframe src="https://drive.google.com/file/d/1kzba8zftWNNVYtkxUmzpyth_VFlOpMk7/preview" width="720" height="240"></iframe>

## Solutions

### Question 1
The following program fragment uses loops. What is the output? 
```cpp
int i = 0; 
while (i <= 4) {
	i = i + 1;
	cout << i << "\n";
}
```
**Solution:**
```cpp
// counts from 1 to 5:
1
2
3
4
5
```

### Question 2
The following program fragment uses loops. What is the output? 
```cpp
int a = 8; 
while (a > 4) {
	cout << a << "\n";
	a--;
}
```
**Solution:**
```cpp
// counts down from 8 to 5
8
7
6
5
```

### Question 3
The following program fragment uses loops. What is the output? 
```cpp
int j = 2, k = 9;
while (j <= k) {
	j++;
	cout << j << ", " << k << "\n";
	k -= 2;
}
```
**Solution:**
```cpp
3, 9
4, 7
5, 5
```

### Question 4
The following program fragment uses loops. What is the output? 
```cpp
int z = 37;
while (z > 0) {
	cout << z % 2;
	z /= 2;
}
cout << "\n";
```
**Solution:** `101001`

### Question 5
The following program fragment contains a `switch` statement. What is the output?
```cpp
int b;
for (b = 1; b < 4; b++) {
	switch(b) {
		case 3:
			cout << "lime\n";
		case 2:
			cout << "orange\n";
			break;
		case 1:
			cout << "lemon\n";
	}
}
``` 
**Solution:**
```
lemon
orange
lime
orange
```

### Question 6
Convert the `while` loop from question #2 into a `for` loop:
```cpp
int a = 8; 
while (a > 4) {
	cout << a << "\n";
	a--;
}
```
**Solution:**
```cpp
for (int a = 8; a > 4; a--) {
	cout << a << "\n";
}
```
