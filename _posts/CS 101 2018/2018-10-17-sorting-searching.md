---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Algorithms II - Sorting & Searching

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   What are some of the algorithms for sorting and searching? 

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

**Searching** for an item and **sorting** a collection of items form an important part of many computer programs. In this lecture, we will analyze four algorithms; two for each of the following common tasks:
- **Searching:** finding the position (or *index*) of a value within a list
- **Sorting:** ordering a list of values

## Searching
Not a day goes by that we don't have to search for something: keys, books, food, or our cellphones. Computers have to do the same. There is so much data stored in a computer that whenever a user asks for something, the computer has to search its memory, looking for the data, and finally making it available to the user. Other searches involve looking for an entry in a database, such as looking up your grades in the school's database. Other search algorithms may search through virtual space, hunting for the best chess move. 

![Emoji Searching](https://cdn.cultofmac.com/wp-content/uploads/2016/05/Gboard-emoji-search.gif)

What if you have to write a program to search a given number in a list of numbers? How will you do it? How will a computer do it?

### Linear Search

Linear search (aka *sequential* search) is the most basic kind of search algorithm. It involves checking each item of the list (beginning to end), until the desired item is found. It compares the desired item with all the items in the list and when the item is matched successfully, it returns the index (or position) of the item in the list, else it returns `-1` (item not found).

```cpp
1. Let index = 0 (the position of the first item in the list)
2. If (desired item = current item), output index of item and stop 
3. Else if (there are more items in the list), go to the next item (index = index + 1), then go to step 2
4. If you get to the end, output -1, card not found.
```

Linear search is applied on unsorted or unordered lists, and works well when there are fewer items in a list. 
![Linear search gif](http://www.globalsoftwaresupport.com/wp-content/uploads/2017/02/ezgif.com-video-to-gif-17.gif)

We say the **complexity** (aka speed) of algorithms is based on the **size of our input**. If we have a list of 9 numbers (shown above), we have to make at most 9 comparisons. If we have 100 items, we have to make at most 100 comparisons. We can graph the speed of the linear search algorithm as a straight *line* (equation: `y = x`, where `y` is the number of comparisons, and `x` is the number of items in your list).


### Binary Search

We've considered the linear search algorithm. Can we do better? Yes, if the list of items is sorted.

Binary search is a more efficient search algorithm that relies on the items of the list already being sorted. 
![Binary search gif](https://ds055uzetaobb.cloudfront.net/image_optimizer/717403b1368376cb6f915e6b4beeb3a7ad54105e.gif)

```cpp
1. Pick the middle item (index = number of remaining items / 2)
2. If desired item found, output index and stop
3. Else if desired item < middle item, repeat with left half
4. Else if desired item > middle card, repeat with right half
5. If you get to the end, output -1, item not found, and stop.
```

With binary search, we perform less comparisons than we did with linear search. Searching through a list of 8 cards, we perform only 3 checks. For a list of 16, we perform at most 4 checks/comparisons. For 32 items, we perform how many comparisons? 5. Do you see a pattern? 

The speed of the binary search algorithm is 2<sup># of comparisons </sup> = # of items in the list. Or log<sub>2</sub>(`x`) = `y`

In the following animation, we can see that binary search may be more *efficient* than linear search in most cases. Can you think of a case when linear search beats binary search? In other words, what is the **best case** and **worst case** for the linear search algorithm? For binary search?
![Binary vs. Linear Searching](https://qph.fs.quoracdn.net/main-qimg-45d8e933eab6b2a4388116d472c402ff)

### Best & Worst Cases

#### Linear Search
- **Best Case:** when the item you're looking for is the first item of the list (# of comparisons performed = 1).
- **Worst Case:** when the item you're looking for is not in the list or at the end (# of comparisons performed = size of the list).

#### Binary Search
- **Best Case:** when the item you're looking for is the middle-most item of the list (# of comparisons performed = 1).
- **Worst Case:** when the item you're looking for is not in the list or at the end (# of comparisons performed = size of the list).

Therefore, linear search performs better than binary search when the item you're looking for is the first item of the list.
![Binary Worst Case](https://www.mathwarehouse.com/programming/images/binary-vs-linear-search/linear-vs-binary-search-worst-case.gif)

## Sorting

Sometimes we may need to sort a collection of items in some particular order (e.g., alphabetically, numerically, chronologically). How do we sort? How can computers sort?

To clarify, the values might be integers, words, cards, or other kinds of objects. We will examine two algorithms:
The values might be integers, or strings or even other kinds of objects. We will examine two algorithms:
- **Selection sort**, which relies on searching and selecting the smallest item
- **Merge sort**, which relies on repeated merging of sections of the list that are already sorted

### Selection Sort

To order a given list using selection sort, we repeatedly select the smallest item and move it to the beginning of a growing sorted list.

```cpp
1. Let index = 0 (the beginning of the list)
2. Use linear search to find the smallest value in the unsorted list
3. Put the current smallest value at index
4. Increment the index (index = index + 1)
5. Repeat step 2 on the remaining unsorted items
6. If you run out of unsorted item, then the list is now sorted, and stop
```

<iframe width="650" height="315" src="https://www.youtube.com/embed/Ns4TPTC8whw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

**Example**: given the following unsorted list, let's sort it using selection sort.
```cpp
5, 2, 8, 1, 9
```

1. Let's start at the beginning of the list.
2. We find the smallest value of the list:
```cpp
	1. assume 5 is the smallest value.
	2. 2 < 5, therefore 2 is the smallest value.
	3. 8 > 2, 2 is still the smallest value.
	4. 1 < 2, therefore 1 is the smallest value.
	5. 9 > 1, 1 is still the smallest value.
	6. We've reached the end of the list (after 5 comparisons). 
	We can conclude that 1 is the smallest value.
```
3. We'll put `1` at the beginning of our list.
```cpp
1				||		5, 2, 8, 9
sorted					unsorted
```
4. Then we'll repeat step 2, find the new smallest value:
```cpp
	1. assume 5 is the smallest value.
	2. 2 < 5, therefore 2 is the smallest value.
	3. 8 > 2, 2 is still the smallest value.
	4. 9 > 2, 2 is still the smallest value.
	5. We've reached the end of the list (after 4 comparisons). 
	We can conclude that 2 is the smallest value.
```
5. We put `2` at the next index of our sorted list.
```cpp
1, 2			||		5, 8, 9
sorted					unsorted
```
6. Then we repeat step 2, finding the new smallest value:
```cpp
	1. assume 5 is the smallest value.
	2. 8 > 5, 5 is still the smallest value.
	3. 9 > 5, 5 is still the smallest value.
	4. We've reached the end of the list (after 3 comparisons). 
	We can conclude that 5 is the smallest value.
```
7. We put `5` at the next index of our sorted list.
```cpp
1, 2, 5			||		8, 9
sorted					unsorted
```
8. Repeat step 2, finding the new smallest value:
```cpp
	1. assume 8 is the smallest value.
	2. 9 > 8, 8 is still the smallest value.
	3. We've reached the end of the list (after 2 comparisons). 
	We can conclude that 8 is the smallest value.
```
9. We put `8` at the next index of our sorted list.
```cpp
1, 2, 5, 8		||		9
sorted					unsorted
```
10. Repeat step 2, finding the new smallest value:
```cpp
	1. assume 9 is the smallest value.
	2. We've reached the end of the list (after 1 comparisons). 
	We can conclude that 9 is the smallest value.
```
11. We put `9` at the next index of our sorted list.
```cpp
1, 2, 5, 8, 9	||		
sorted					unsorted
```
12. According to step 6, we have no more items left to sort. Our sorted list is `1, 2, 5, 8, 9`.

Let's analyze the speed of the selection sort algorithm. When we had a list of 5 items, it took `5 + 4 + 3 + 2 + 1` or `15` comparisons.
- For 6 items, it would take us `6 + 5 + 4 + 3 + 2 + 1` or `21` comparisons.
- For 7 items, it would take us `7 + 6 + 5 + 4 + 3 + 2 + 1` or `28` comparisons.
- For 8 items, it would take us `8 + 7 + 6 + 5 + 4 + 3 + 2 + 1` or `36` comparisons.
- For 9 items, it would take us `9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1` or `45` comparisons.
- For 10 items, it would take us `10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1` or `55` comparisons.

Do you see a pattern? Although we may not know the exact equation for the graph, we know the complexity of selection sort grows more and more each time. In fact, it looks a lot like the graph of *n*<sup>2</sup>. 
![Exponential Graph](http://nathanmlong.com/images/posts/big_o/introductions.png)

Therefore, we say that the complexity of the selection sort algorithm is **exponential**.

### Merge Sort
When we use merge sort to order a list, we repeatedly merge sorted sub-lists of the entire list – starting from sub-lists consisting of a single item each. In other words, we sort by **dividing and conquering**.

````cpp
1. Divide the unsorted list into sublists, each containing 1 element (a list of 1 element is considered sorted).
2. Merge sublists to produce new sorted sublists 
3. Stop when you've merged all sublists back into a single list. This will be the sorted list.
````

<iframe width="650" height="315" src="https://www.youtube.com/embed/XaqR3G_NVoo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

**Example:** let's sort the list `14, 7, 3, 12, 9, 11, 6, 12` using merge sort.
![Merge Sort Example](https://www.studytonight.com/data-structures/images/merge-sort-working.png)

Merge sort is quite fast and has a complexity of `n log n` where *n* is the size of the list. This is because whenever we divide a list in half in each step, it can be represented by a [logarithmic function](https://en.wikipedia.org/wiki/Logarithm) (log<sub>2</sub>8 = 3 because 2<sup>3</sup> is 8) and we still have to split into *n* sublists.

## Complexity
As a summary of the complexities of the algorithms we've reviewed, where *n* is the size of the list
- *linear search*: **average case** is `n`, **best** is `1` (first item = desired item), and **worst** is `n` (desired item not in list)
- *binary search*: **average case** is `log n`, **best** is `1` (middle item = desired item), and **worst** is `log n` (desired item not in list)
- *selection sort*: **average case** is `n`<sup>2</sup>, **best** is `n`<sup>2</sup>, and **worst** is `n`<sup>2</sup>
- *selection sort*: **average case** is `n log n`, **best** is `n log n`, and **worst** is `n log n`

The graphs may look like this:
![Complexity Graphs](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Comparison_computational_complexity.svg/1200px-Comparison_computational_complexity.svg.png)

## Additional Resources
- [AlgoRythmics](https://www.youtube.com/channel/UCIqiLefbVHsOAXDAxQJH7Xw), demonstrates algorithms through dance
- [Sorting Algorithms Animations - Toptal](https://www.toptal.com/developers/sorting-algorithms) - graphically animations additional sorting algorithms
- [Sorting Algorithms Animations -  Zapponi](http://sorting.at/) - more sorting algorithms animations
- [Sorting Algorithms Animations - VisualGo](https://visualgo.net/bn/sorting) - more sorting algorithms animations with user-defined lists
- [Sorting Algorithms For Color - morolin](https://imgur.com/gallery/voutF) - sorting algorithms for sorting by color