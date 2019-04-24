---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Programming Sprints to Try

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   To practice and develop your C++ fluency, try these programming sprints.
   
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

**Prompts:**
- [Program 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-1): prints a user-inputted number
- [Program 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-2): prints sum of two user-inputted numbers
	- [Variation 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-1) entirely in `main`
	- [Variation 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-2), with a function responsibly for entering a number, `enterNumber`
	- [Variation 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-3), with two functions, `enterNumber` and `getSum`
- [Program 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-3): prints quotient and remainder of two user-inputted numbers
	- [Variation 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-1-1) entirely in `main`
	- [Variation 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-2-1), with two function, `getQuotient` and `getRemainder`
	- [Variation 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-3-1), with a function `getSolution` which returns a vector containing quotient and remainder
- [Program 4](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-4): prints whether a user-inputted year is a leap year
	- [Variation 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-1-2) entirely in `main`
	- [Variation 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-2-2) entirely in `main`, but checks if a valid year is entered
	- [Variation 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-3-2) entirely in `main`, but continues asking until a valid year is entered
- [Program 5](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-5): prints the `10` x `10` multiplication table
- [Program 6](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-6): checks if a user-inputted char is a vowel or consonant
	- [Variation 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-1-3), with an `if` statement
	- [Variation 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-2-3), with an array
	- [Variation 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-3-3), with a vector
	- [Variation 4](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-4-3), with a function responsible for vowel-checking
- [Program 7](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#program-7): counts how many vowels and how many consonants in an entered sentence
	- [Variation 1](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-1-4), with `isVowel` function - counts non-letters as consonants
	- [Variation 2](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-2-4), considers only letters by checking ASCII ranges in `isLetter` function
	- [Variation 3](https://ramnauth.github.io/cs%20102/coding%20challenges/2018/10/15/performance-1/#variation-3-4), considers only letters by `isalpha` function in `isLetter` function
	
		
## Program 1
Write a program that prints a number entered by the user. (*5 minutes*)

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

## Program 2
Write a program that calculates the sum of two user-inputted numbers. (*5 minutes*)

### Variation 1

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

### Variation 2

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

### Variation 3

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

## Program 3
Write a program that prints the quotient and remainder of two user-inputted numbers. (*5 minutes*)

### Variation 1

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

### Variation 2
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

### Variation 3
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

## Program 4
Write a program that prints whether a user-inputted number (year) is a leap year. (*5 minutes*)

### Variation 1

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

### Variation 2

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

### Variation 3

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

## Program 5
Write a program that generates a 10 by 10 multiplication table (shown below). Formatting isn't necessary. (*5 minutes*)

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

## Program 6
Write a program that checks if a user-inputted character is a vowel or a consonant (*8 minutes*)

### Variation 1
```cpp
#include <iostream>

using namespace std;

int main() {
    char sym;
    cout << "Enter a character: ";
    cin >> sym;

    if (sym == 'a' || sym == 'e' || sym == 'i' || sym == 'o' || sym == 'u' ||
        sym == 'A' || sym == 'E' || sym == 'I' || sym == 'O' || sym == 'U') {
        cout << sym << " is a vowel." << endl;
    } else {
        cout << sym << " is a consonant." << endl;
    }
	
	return 0;
}
```

### Variation 2
```cpp
#include <iostream>

using namespace std;

int main() {
    char vowels[5] = {'a', 'e', 'i', 'o', 'u'};
    
	bool isVowel = false; // assume it's a consonant unless proven to be a vowel
    
	char c;
    cout << "Enter a symbol: " << endl;
    cin >> c;

    for (int i = 0; i < 5; i++) {
        if (c == vowels[i]) {
            isVowel = true;
        }
    } 
    
    if (isVowel == true) {
        cout << c << " is a vowel." << endl;
    } else {
        cout << c << " is a consonant." << endl;
    }
	
    return 0;
}
```

### Variation 3
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    vector<char> vowels = {'a', 'e', 'i', 'o', 'u'};

    /*
	vowels.push_back('a');
    vowels.push_back('e');
    vowels.push_back('i');
    vowels.push_back('o');
    vowels.push_back('u');
	*/

    bool isVowel = false; // assume it's a consonant unless proven to be a vowel
	
    char c;
    cout << "Enter a symbol: " << endl;
    cin >> c;

    for (int i = 0; i < 5; i++) {
        if (c == vowels.at(i)) {
            isVowel = true;
        }
    } 
    
    if (isVowel == true) {
        cout << c << " is a vowel." << endl;
    } else {
        cout << c << " is a consonant." << endl;
    }
	
    return 0;
}
```

### Variation 4
```cpp
#include <iostream>

using namespace std;

bool isVowel(char sym) {
	if (sym == 'a' || sym == 'e' || sym == 'i' || sym == 'o' || sym == 'u' ||
        sym == 'A' || sym == 'E' || sym == 'I' || sym == 'O' || sym == 'U') {
        return true;
    } else {
        return false;
    }
}

int main() {
	char c;
    cout << "Enter a symbol: " << endl;
    cin >> c;
	
	bool provenVowel = false;

    for (int i = 0; i < 5; i++) {
        if (isVowel(c)) {
            provenVowel = true;
        }
    } 
    
    if (provenVowel == true) {
        cout << c << " is a vowel." << endl;
    } else {
        cout << c << " is a consonant." << endl;
    }
	
    return 0;
}
```

## Program 7
Write a program that counts how many vowels and how many consonants in an user-inputted sentence (*10 minutes*)

### Variation 1

```cpp
#include <iostream>
#include <vector>
#include <string>

using namespace std;

bool isVowel(char sym) {
    if (sym == 'a' || sym == 'e' || sym == 'i' || sym == 'o' || sym == 'u' ||
        sym == 'A' || sym == 'E' || sym == 'I' || sym == 'O' || sym == 'U') {
        return true;
    } else {
        return false;
    }
}

int main() {
    
    string sentence = "";
    cout << "Enter a word/sentence: " << endl;
    getline(cin, sentence);

    int vowelCounter = 0;
    int consonantCounter = 0;

    for (int i = 0; i < sentence.size(); i++) {
		if (isVowel(sentence.at(i)))
			vowelCounter++;
		else 
			consonantCounter++;
    }
    cout << "Consonants = " << consonantCounter << "; Vowels = " << vowelCounter << endl;
    
    return 0;
}
```

### Variation 2

```cpp
#include <iostream>
#include <vector>
#include <string>

using namespace std;

bool isVowel(char sym) {
    if (sym == 'a' || sym == 'e' || sym == 'i' || sym == 'o' || sym == 'u' ||
        sym == 'A' || sym == 'E' || sym == 'I' || sym == 'O' || sym == 'U') {
        return true;
    } else {
        return false;
    }
}

bool isLetter(char sym) {
    int val = (int)sym; // give me the ASCII value of the char
    if ((val >= 65 && val <= 90) || (val >= 97 && val <= 122)) {
        return true; // it's a letter
    } else {
        return false;
    }
}

int main() {
    
    string sentence = "";
    cout << "Enter a word/sentence: " << endl;
    getline(cin, sentence);

    int vowelCounter = 0;
    int consonantCounter = 0;

    for (int i = 0; i < sentence.size(); i++) {
        if (isLetter(sentence.at(i))) {
            if (isVowel(sentence.at(i)))
                vowelCounter++;
            else 
                consonantCounter++;
        }
    }
    cout << "Consonants = " << consonantCounter << "; Vowels = " << vowelCounter << endl;
    
    return 0;
}
```

### Variation 3

```cpp
#include <iostream>
#include <vector>
#include <string>

using namespace std;

bool isVowel(char sym) {
    if (sym == 'a' || sym == 'e' || sym == 'i' || sym == 'o' || sym == 'u' ||
        sym == 'A' || sym == 'E' || sym == 'I' || sym == 'O' || sym == 'U') {
        return true;
    } else {
        return false;
    }
}

bool isLetter(char sym) {
    int val = isalpha(sym);
    if (val != 0) { // it's a letter
        return true; 
    } else {
        return false;
    }
}

int main() {
    
    string sentence = "";
    cout << "Enter a word/sentence: " << endl;
    getline(cin, sentence);

    int vowelCounter = 0;
    int consonantCounter = 0;

    for (int i = 0; i < sentence.size(); i++) {
        if (isLetter(sentence.at(i))) {
            if (isVowel(sentence.at(i)))
                vowelCounter++;
            else 
                consonantCounter++;
        }
    }
    cout << "Consonants = " << consonantCounter << "; Vowels = " << vowelCounter << endl;
    
    return 0;
}
```