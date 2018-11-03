---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Classroom Coding Sprint - Prof. League's 2012-2016 Quizzes

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
categories: [CS 102, Coding Challenges]
tags: [C++]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

Here are the solutions for the following quizzes/exams:
- [Fall 2016 Quiz #2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#fall-2016---quiz-2)
- [Fall 2016 Quiz #3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#fall-2012---quiz-3)
- [Fall 2012 Quiz #4](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#fall-2012---quiz-4)
- [Fall 2012 Quiz #6](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#fall-2012---quiz-6)
- [Fall 2015 Quiz #1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#fall-2015---quiz-1)
- [Fall 2015 Quiz #2]

## [Fall 2016 - Quiz 2](https://drive.google.com/file/d/1hHGyVfnsw_9XKkHaySpc6K_bDmFiNsap)

### Question 1
Which of the following statements prints exactly this text, as shown:
```
We the
PEOPLE
```
Select all that apply.
```cpp
cout << "We the PEOPLE" << endl; 				// A
cout << "We the" << "endl" << "PEOPLE" << "endl";		// B
cout << "We" << " the" << endl << "PEOPLE" << endl;		// C
cout << "We the" << endl << "PEOPLE" << endl; 			// D
cout << "WE the" << endl << "people";				// E
```
**Solution:**
```cpp
cout << "We the PEOPLE" << endl; 				// prints "We the PEOPLE"
cout << "We the" << "endl" << "PEOPLE" << "endl";		// prints "We the endl PEOPLE"
cout << "We" << " the" << endl << "PEOPLE" << endl;		// prints correct output
cout << "We the" << endl << "PEOPLE" << endl; 			// prints correct output
cout << "WE the" << endl << "people";				// prints with capital "E" in "WE"
```
Only options **c** and **d** produce the required output.

### Question 2
Given a variable `maxDays = 14`, which statement prints `14`?
```cpp
cout >> maxDays;		// A
cout << maxDays;		// B
cout << "maxDays";		// C
print maxDays;			// D
```
**Solution:**
```cpp
cout >> maxDays;		// arrows are facing the wrong way for cout
cout << maxDays;		// prints correct answer
cout << "maxDays";		// prints the word "maxDays" not the value
print maxDays;			// wrong command for printing, use cout
```
Only option **b** produces the required output.

### Question 3
Circle and describe any syntax errors in this program:
```cpp
#include <iostream>
using namespace;
INT main( )
{
	int score = 100;
	cout << 'Hello world.' << endl
	cout < score < '%';
	return 0;
}
```
**Solution:**
- Missing namespace `std`
- Should lowercase `INT`
- Need double quotes around `“Hello world”`
- Need semi-colon after `endl`
- Need double less-than `<<` on second `cout`

### Question 4
Below is a simple C++ program containing a calculation and some output. What would it output when you run it?
```cpp
#include <iostream>
using namespace std;
int main()
{
	int lisa = 8;
	int bart = lisa + 2;
	int maggie = bart - 7;
	cout << maggie << ", " << bart << lisa << endl;
	return 0;
}
```
**Solution:** will output `3, 108`

### Question 5
The following program uses a variety of arithmetic operators and mathematical functions. What does it output? You can write each line of output to the right of the corresponding `endl`.
```cpp
#include <iostream>
#include <cmath>
using namespace std;
int main()
{
	cout << 9 / 2            << endl; // _______
	cout << 7 / 2.0          << endl; // _______
	cout << 17 % 2           << endl; // _______
	cout << 31 % 7           << endl; // _______
	cout << pow(3,3)         << endl; // _______
	cout << sqrt(25)         << endl; // _______
	cout << floor(9.8)       << endl; // _______
	cout << sqrt(pow(2,4))+1 << endl; // _______
	return 0;
}
```
**Solution:**
```cpp
#include <iostream>
#include <cmath>
using namespace std;
int main()
{
	cout << 9 / 2            << endl; // 4
	cout << 7 / 2.0          << endl; // 3.5
	cout << 17 % 2           << endl; // 1
	cout << 31 % 7           << endl; // 3
	cout << pow(3,3)         << endl; // 27
	cout << sqrt(25)         << endl; // 5
	cout << floor(9.8)       << endl; // 9
	cout << sqrt(pow(2,4))+1 << endl; // 5
	return 0;
}
```

## [Fall 2012 - Quiz 3](https://drive.google.com/file/d/1kzba8zftWNNVYtkxUmzpyth_VFlOpMk7)

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

## [Fall 2012 - Quiz 4](https://drive.google.com/file/d/1_TU7Ed6hRaY5-3owg6zErfiaGmzNOLoM)

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

## [Fall 2012 - Quiz 6](https://drive.google.com/file/d/1ESM_wki49RVnEGK4-JuuyVcZrozbamCe)

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

## [Fall 2015 - Quiz 1](https://drive.google.com/file/d/1VKqefqVuFkRsoQGp2LKK6NXAAx_Aq_vX/)

### Question 1
Same as [Fall 2016 - Quiz 2 - Question 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#question-1)

### Question 2
Same as [Fall 2016 - Quiz 2 - Question 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#question-2)

### Question 3
Which of these are valid C++ comments that will be ignored by the compiler? Select all that apply.
```
a. /* Hello world */
b. "Hello world"
c. # Hello world
d. /* Hello world
e. -- Hello world
f. (( Hello world ))
g. // Hello world
```

**Solution:**
```cpp
a. /* Hello world */ 
g. // Hello world
```
Options **a** and **g** are valid comments in C++.

### Question 4
Same as [Fall 2016 - Quiz 2 - Question 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#question-3)

### Question 5
Same as [Fall 2016 - Quiz 2 - Question 4](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#question-4)

## [Fall 2015 - Quiz 2](https://drive.google.com/file/d/1ku6tsugmiJ6BwMZx9mmPO6W1qQAWAW58)

### Question 1
Same as [Fall 2016 - Quiz 2 - Question 5](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/08/class-sprint-3/#question-5)

### Question 2
Suppose that we have a `main` program containing this declaration:
```cpp
string courseTitle;
```
Briefly explain the difference between these two operations:
```cpp
cin >> courseTitle;			//a
getline(cin, courseTitle);	//b
```

**Solution:**
`cin` reads only one word from the input and leaves the 'cursor' just before the first space or newline. On the other hand, `getline` reads an entire line up to the user pressing enter.

### Question 3
The following program does some arithmetic on `char` types. What does it output?
```cpp
#include <iostream>
using namespace std;
int main()
{
    char one = 'I';
    char fiv = 'V';
    char x   = one + 4;
    char y   = fiv + 2;
    cout << x << x << y << one << fiv << endl;
    return 0;
}
```

**Solution:** `MMXIV`
```cpp
#include <iostream>
using namespace std;
int main()
{
    char one = 'I';
    char fiv = 'V';
    char x   = one + 4;	// means add 4 to the ASCII value of 'I' or 4 letters after = M
    char y   = fiv + 2; // means add 2 to the ASCII value of 'V' or 2 letters after = X
    cout << x << x << y << one << fiv << endl;
    return 0;
}
```

### Question 4
The program below uses conditional statements (specifically, an `if-else` chain). Given the values of `x` and `y` as inputs, what does the program output?
- `x` = 6; `y` = 3; Output: _________
- `x` = 7; `y` = 7; Output: _________
- `x` = 5; `y` = 5; Output: _________
- `x` = 7; `y` = 10; Output: _________

```cpp
#include <iostream>
using namespace std;
int main()
{
    int x, y;
    cout << "Enter two integers: ";
    cin >> x >> y;
    if(x < 7)
    {
        cout << "A";
    }
    else if(y < 9)
    {
        cout << "B";
    }
    else
    {
        cout << "C";
    }
    return 0;
}
```
**Solutions:**

- `x` = 6; `y` = 3; Output: `A`
- `x` = 7; `y` = 7; Output: `B`
- `x` = 5; `y` = 5; Output: `A`
- `x` = 7; `y` = 10; Output: `C`

## [Fall 2015 - Quiz 3](https://drive.google.com/file/d/1V8F5_JfaOqeovBbNNhuHKCNPCyhJ_BtF)

### Question 1 
The program on this page uses nested conditional statements. Given the values below as inputs, what does the program output?
- `fred` = 6; `wilma` = 3; Output: _________
- `fred` = 7; `wilma` = 7; Output: _________
- `fred` = 3; `wilma` = 6; Output: _________
- `fred` = 6; `wilma` = 9; Output: _________
- `fred` = 5; `wilma` = 1; Output: _________
```cpp
#include <iostream>
using namespace std;
int main()
{
    int fred, wilma;
    cin >> fred >> wilma; // inputs given above
    if(fred < wilma)
    {
        if(wilma > 5) cout << "A";
        else cout << "B";
        cout << "C";
    }
    if(fred == wilma)
    {
        cout << "D";
    }
    else
    {
        if(fred > 5) cout << "E";
        cout << "F";
    }
}
```
**Solutions:**

- `fred` = 6; `wilma` = 3; Output: `EF`
- `fred` = 7; `wilma` = 7; Output: `D`
- `fred` = 3; `wilma` = 6; Output: `ACF`
- `fred` = 6; `wilma` = 9; Output: `ACEF`
- `fred` = 5; `wilma` = 1; Output: `F`

### Question 2 
This is a similar problem, but this program uses a `while` loop. What does the program output?

```cpp
#include <iostream>
using namespace std;
int main()
{
    int carol = 3;
    while(carol > 1)
    {
        cout << carol << "\n";
        if(carol % 2 == 0) {
            carol /= 2;
        }
        else {
            carol = carol * 3 + 1;
        }
    }
    return 0;
}
```

**Solution:**
```cpp
3
10
5
16
8
4
2
```

## [Fall 2015 - Quiz 4](https://drive.google.com/file/d/1y2VYUnRXQgVWzCvqLI0OO6R7EMisb9P1)
### Question 1
This program contains a loop. What does it output?
```cpp
#include <iostream>
using namespace std;
int main()
{
    int k = 9;
    while(1)
    {
        if(k % 2 == 0)
        {
            cout << k*k << "\n";
        }
        if(k % 5 == 0)
        {
            break;
        }
        k--;
    }
    cout << k << "\n";
    return 0;
}
```

**Solution:**
```cpp
64
35
5
```

### Question 2 
Here is another program with a loop. What does it output?
```cpp
#include <iostream>
using namespace std;
int main()
{
    int x = 0;
    for(int i = 1; i < 8; i+=2)
    {
        cout << i << "\n";
        x += i;
    }
    cout << x << "\n";
    return 0;
}
```

**Solution:**
```cpp
1
3
5
7
16
```

## [Fall 2015 - Quiz 6](https://drive.google.com/file/d/14M8dSEYQxZ5xNRsoA3kKSiyVj2hoW8tP)

### Question 1
The following program uses an array. What does it output?
```cpp
int main()
{
    const int SZ = 5;
    int g[SZ];
    int x = 5;
    for(int i = 0; i < SZ; i++)
    {
        x += i;
        g[i] = x+1;
    }
    for(int i = SZ-1; i > 0; i--)
    {
        cout << g[i] << "\n";
    }
    return 0;
}
```

**Solution:**
```cpp
16
12
9
7
```

### Question 2 
The following program uses nested function calls with return values. What is its output?
```cpp
int trot(int x)
{
    if(x > 4) {
        return x - 3;
    }
    else {
        return x - 1;
    }
}

int thaw(int y)
{
    return y+5;
}

int main()
{
    cout << trot(3) << "\n";
    cout << thaw(4) << "\n";
    cout << trot(thaw(5)) << "\n";
    cout << thaw(trot(thaw(6))) << "\n";
    return 0;
}
```

**Solution:**
```cpp
2
9
7
13
```

## [Fall 2015 - Final Exam](https://drive.google.com/file/d/1_6XOPCMQWJ4QKigmBfj-IVo2EOxD5slh/)
**Solutions** posted [here](https://liucs.net/cs102f15/e2pr.sol.pdf)