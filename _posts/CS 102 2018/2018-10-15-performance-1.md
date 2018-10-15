---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Performance Assessment - Week 1 (Oct. 15 - 19)

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Upload link provided below. Prompts will be posted after assessment. 

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

**Submission portal**: [https://goo.gl/forms/IQfsFiHbI9lS5HQs2](https://goo.gl/forms/IQfsFiHbI9lS5HQs2)

1. Multiple submissions allowed
2. Title each program
3. Use comments to explain what's happening in your program
4. Use style guidelines to keep organized

## Solutions
- [Program 1](): prints a user-inputted number
- [Program 2](): prints sum of two user-inputted numbers
	- [Variation 1]() entirely in `main`
	- [Variation 2](), with a function responsibly for entering a number, `enterNumber`
	- [Variation 3](), with two functions, `enterNumber` and `getSum`
- [Program 3](): prints quotient and remainder of two user-inputted numbers
	- [Variation 1]() entirely in `main`
	- [Variation 2](), with two function, `getQuotient` and `getRemainder`
	- [Variation 3](), with a function `getSolution` which returns a vector containing quotient and remainder
- [Program 4](): prints whether a user-inputted year is a leap year
	- [Variation 1]() entirely in `main`
	- [Variation 2]() entirely in `main`, but checks if a valid year is entered
	- [Variation 3]() entirely in `main`, but continues asking until a valid year is entered
- [Program 5](): prints the `10` x `10` multiplication table


### Program 1
**Prompt** (*5 minutes*): print a number entered by the user

```cpp
#include <iostream> 

using namespace std;

int main() {
	int num; 
	cout << "Enter a number: ";
	cin >> num;
	
	cout << "The number you have entered is: " << num << endl;
	
	return 0;
}
```

### Program 2
**Prompt** (*5 minutes*): write a program that calculates the sum of two user-inputted numbers

#### Variation 1

```cpp
#include <iostream> 

using namespace std;

int main() {
	int a, b;
	cout << "Enter a number: ";
	cin >> a;
	cout << "Enter another number: ";
	cin >> b;
	
	cout << "The sum of " << a << " and " << b << " is " << a + b << endl;
	
	return 0;
}
```

#### Variation 2

```cpp
#include <iostream> 

using namespace std;

int enterNumber() {
	int num; 
	cout << "Enter a number: ";
	cin >> num;
	return num;
}

int main() {
	int a = enterNumber();
	int b = enterNumber();
	
	cout << "The sum of the numbers " << a << " and " << b << " is " << a + b << endl;
	
	return 0;
}
```

#### Variation 3

```cpp
#include <iostream> 

using namespace std;

int enterNumber() {
	int num; 
	cout << "Enter a number: ";
	cin >> num;
	return num;
}

int getSum(int num_1, int num_2) {
	return num_1 + num_2;
}

int main() {
	int a = enterNumber();
	int b = enterNumber();
	
	int sum = getSum(a, b)
	cout << "The sum of the numbers " << a << " and " << b << " is " << sum << endl;
	
	return 0;
}
```

### Program 3
**Prompt** (*5 minutes*): write a program that prints the quotient and remainder of two user-inputted numbers

#### Variation 1

```cpp
#include <iostream> 

using namespace std;

int main() {
	int a, b;
	cout << "Enter a number: ";
	cin >> a;
	cout << "Enter another number: ";
	cin >> b;
	
	cout << "Quotient = " << a / b << " with Remainder = " << a % b << endl;
	
	return 0;
}
```

#### Variation 2
```cpp
#include <iostream> 

using namespace std;

int enterNumber() {
	int num; 
	cout << "Enter a number: ";
	cin >> num;
	return num;
}

int getQuotient(int a, int b) {
	return a / b;
}
int getRemainder(int a, int b) {
	return a % b;
}

int main() {
	int a = enterNumber();
	int b = enterNumber();
	
	int quotient = getQuotient(a, b);
	int remainder = getRemainder(a, b);
	
	cout << "Quotient = " << quotient << " with Remainder = " << remainder << endl;
	
	return 0;
}
```

#### Variation 3
```cpp
#include <iostream> 
#include <vector>

using namespace std;

int enterNumber() {
    int num = 0;
    cout << "Enter a number: ";
    cin >> num; 
    return num;
}

vector<int> getSolution(int a, int b) {
    vector<int> solution(2);
    int q = a / b;
    int r = a % b;

    solution.at(0) = q;
    solution.at(1) = r;
	
	// ALTERNATIVE to declaring/defining vector solution
	// vector<int> solution;
    // solution.push_back(q);
    // solution.push_back(r);

    return solution;
}

int main(){
    int a = enterNumber();
    int b = enterNumber();

    vector<int> v = getSolution(a, b);

    cout << "Quotient = " << v.at(0) << "; Remainder = " << v.at(1) << endl;
    return 0;
}
```

### Program 4
**Prompt** (*5 minutes*): prints whether a user-inputted number (year) is a leap year or not

#### Variation 1

```cpp
#include <iostream> 

using namespace std;

int main() {
	int year = 2018;
	cout << "Enter a number: ";
	cin >> year;
	
	if (year % 4 == 0) {
		cout << "The year " << year << " is a leap year." << endl;
	} else {
		cout << "The year " << year << " is NOT a leap year." << endl;
	}
	
	return 0;
}
```

#### Variation 2

```cpp
#include <iostream> 

using namespace std;

int main() {
	int year = 2018;
	cout << "Enter a number: ";
	cin >> year;
	
	if (year < 0) {
		cout << "That is not a valid year!" << endl;
	} else {
		if (year % 4 == 0) {
			cout << "The year " << year << " is a leap year." << endl;
		} else {
			cout << "The year " << year << " is NOT a leap year." << endl;
		}
	}
	
	return 0;
}
```

#### Variation 3

```cpp
#include <iostream> 

using namespace std;

int main() {
	int year = -1;
	
	while (year < 0) {
		cout << "Enter a number: ";
		cin >> year;
	} 
	
	if (year % 4 == 0) {
		cout << "The year " << year << " is a leap year." << endl;
	} else {
		cout << "The year " << year << " is NOT a leap year." << endl;
	}
	
	return 0;
}
```

### Program 5
**Prompt** (*5 minutes*): generates a 10 by 10 multiplication table (shown below). Disregard formatting.
![Multiplication Table](https://i.pinimg.com/originals/67/37/e5/6737e5ce801751ef91200e0df886921a.gif)

```cpp
#include <iostream>

using namespace std;

int main() {
    for (int row = 1; row <= 10; row++) {
        for (int col = 1; col <= 10; col++) {
            int cell = row * col; 
            cout << cell << " ";
        } 
        cout << endl;
    }
    return 0;
}
```
