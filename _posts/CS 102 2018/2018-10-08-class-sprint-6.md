---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Prof. League's Quiz 6

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
<iframe src="https://drive.google.com/file/d/1ESM_wki49RVnEGK4-JuuyVcZrozbamCe/preview" width="720" height="240"></iframe>

## Solutions

### Question 1
What is the output of the following program?
```cpp
void quirt();
void blirp();

int main() {
	quirt();
	blirp();
	cout << "\n";
	return 0;
}

void blirp() {
	cout << "X";
	quirt();
	quirt();
	cout << "Y";
	quirt();
}

void quirt() {
	cout << "B";
}
```
**Solution:** `BXBBYB`

### Question 2
What is the output of the following program? 
```cpp
void blerk(int a) {
	cout << a << ", ";
}

void torp(int b) {
	int a = b + 1;
	blerk(b);
	blerk(a);
}

int main() {
	torp(3);
	torp(7);
	cout << "\n";
	return 0;
}
```
**Solution:** `3, 4, 7, 8,`

### Question 3
What is the output of the following program?
```cpp
int trak(int x, int y) {
	return x * x * y;
}

int stap(int z) {
	return trak(z, trak(z + 1, z));
}

int main() {
	cout << stap(2) << "\n";
	cout << stap(4) << "\n";
	return 0;
}
```
**Solution:**
```cpp
72
1600
```