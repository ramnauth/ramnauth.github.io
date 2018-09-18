---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Text Encoding & Compression

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   How can we represent text differently and more efficiently?

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
In previous lessons, we focused heavily on representing numbers in different ways (such as in binary or hexadecimal).
How can we go a step further and represent words and sentences in a different and more concise way? 


## Character Encoding

Letters, words, sentences, paragraphs and other text are created from **characters**. A character could be any letter between `A` to `Z`, any Latin letter ([`á`](https://www.w3.org/International/questions/qa-what-is-encoding-data/225.png)), or any Chinese ideograph ([`請`](https://www.w3.org/International/questions/qa-what-is-encoding-data/35531.png)), and so on.

A group of characters is called a **character set**. An example character set for writing in English would include the characters `A` to `Z`, `0` to `9`, punctuation marks (`!`, `?`, `;`), and symbols to denote spaces (`_`), new lines, and more. 
However, some characters look similar to another that it's hard to distinguish between them. For example, `l` (the letter) and `1` (the number). One solution is to associate each character with a number, called a **code point**. 

So, in a computer, characters are stored as a series of bits. In other words, characters are stored in the computer using a special code that can be deciphered only by knowing the **character encoding**. Without knowing the encoding, you won't be able to read the text. 
This is similar to *morse code* which uses a series of dots and dashes to represent characters/letters. If you did not know how letters are encoded in morse, you wouldn't be able to read the message: [.... . .-.. .-.. --- / .-- --- .-. .-.. -..](http://morsecode.world/m/eJxjYhIR8XD18fFXCPcP8nEBABS9A0k=).

### ASCII 

[**ASCII**](https://simple.wikipedia.org/wiki/ASCII) (*American Standard Code for Information Interchange*) is well known for encoding English characters. When it was developed in the early 1960s, it included a 7-bit mapping of upper and lower case letters, numbers, and other useful symbols. Because it uses 7 bits, we can represent up to 2<sup>7</sup> or 128 characters. A brief breakdown of the 'sections' of the ASCII table:
- Code points 0 through 31 are called *control characters*, many of which are now obsolete.
- Code point 32 represents a space
- Code points 33 through 63 are mostly representations of punctuation
- Code points 48 through 57 represent numbers 0 to 9. In ASCII binary, numerals are easy to recognize because they all start with `011`. For instance, the numeral `7` can be represented as `55` in ASCII decimal or `0110111` in ASCII binary. The first 3 bits `011` denote that it is a numeral, and the following 4 bits `0111` is the value `7`. 
- Code points 64 through 95 are mostly upper case letters. In ASCII binary, upper case letters all start with `10` and the remaining 5 bits give the position of the letter in the alphabet. For example, `10 01011` is the eleventh letter but upper case (`K`).
- Code points 96 through 127 are mostly lower case letters. In ASCII binary, these start with `11` and the remaining 5 bits give the position of the letter in the alphabet. For example, `10 01011` is the eleventh letter but lower case (`k`).

### Unicode

One problem with ASCII is that it only represent 128 characters. But what if we wanted to write `¿Cómo estás?` or `你好`? ASCII is only limited to English characters. So it doesn't represent the different symbols, accents, and alphabets in other cultures. 

As a result, ASCII has a significant upgrade. Instead of using 7-bits, it became possible to use an 8th bit to indicate an extra 128 characters. Each of the 256 ASCII characters, 8 bits or 1 **byte** was allocated to its code point. 

This caused another problem. Most other 8-bit encodings at the time agreed on the old 128 characters in ASCII, but conflicted with the new 128 characters as explained in the [ISO/IEC 8859 specification](https://en.wikipedia.org/wiki/ISO/IEC_8859). 

To resolve incompatible encodings across different languages and cultures, the **Unicode Consortium** attempted (and is still attempting) to create a single encoding that would contain every character and symbol used in every language. You can browse the many code charts on the [Unicode website](http://www.unicode.org/charts/). 

How is this possible? As shown in the Unicode code charts, most code points fit in 16 bits (aka 2 bytes). But this means there are only 2<sup>16</sup> or 65,636 characters that we can represent. There are obviously much more than 65,636 characters in the world, so Unicode has several **planes** (like in geometry). Each plane has different code points, which you can see here: [Unicode planes & code point ranges](https://en.wikipedia.org/wiki/Plane_(Unicode)#Overview). Designating a bit or two to indicate which plane to use, allows us to represent `65,636 times the number of planes` characters. <br>

<iframe width="650" height="315" src="https://www.youtube.com/embed/MijmeoH9LT4?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Text Compression

We *encode* text so a computer (which only 'speaks' binary) can understand it. However, sometimes using so many bits to encode a simple character like `A` (= `01000001`) is an inefficient use of bits/space/memory. The goal of **compression** is to reduce the number of bits used for a character's code point. In general, to *compress* something is to squish it into something smaller.

### Keyword Compression

This type of compression method simply replaces frequently used words (aka *keywords*) with a single character. For example, let's try compress the following paragraph (from *Peter Pan*) by its keywords:

> All children, except one, grow up. They soon know that they will grow up, `and` `the` way Wendy knew `was` this. One day when `she` `was` two years old `she` `was` playing in a garden, `and` `she` plucked another flower `and` ran with it to her mother. I suppose `she` must have looked rather delightful, for Mrs Darling put her hand to her heart `and` cried, 'Oh, why can't you remain like this for ever!' This `was` all that passed between them on `the` subject, but henceforth Wendy knew that `she` must grow up. You always know after you are two. Two is `the` beginning of the end.

Then, we'll determine which words appeared the most (or appeared *frequently*). We find that the word `she` appeared 5 times, `was` 4 times, `the` 4 times, and `and` appeared 4 times. We can continue finding more frequently used words, but we can stop here. 

Let's now replace these words with each their own character. For `she`, we'll put the `@`, for `was` put `%`, `the` put `~`, and for `and` put `&`. It doesn't matter what symbol you use as long as you state what word the symbol represents. The compressed paragraph:

> All children, except one, grow up. They soon know that they will grow up, & ~ way Wendy knew % this. One day when @ % two years old @ % playing in a garden, & @ plucked another flower & ran with it to her mother. I suppose @ must have looked rather delightful, for Mrs Darling put her hand to her heart & cried, 'Oh, why can't you remain like this for ever!' This % all that passed between them on ~ subject, but henceforth Wendy knew that @ must grow up. You always know after you are two. Two is ~ beginning of ~ end.

The new and compressed paragraph is 519 characters, which is an improvement from the original paragraph of 553 characters. We managed to remove 34 characters, reducing the size of the paragraph by more than 6%. 

A problem with keyword compression is that the keywords (words that we most frequently use) are often short. For a list of the most common words in English, see [Wikipedia's list based on the Oxford English Corpus](https://en.wikipedia.org/wiki/Most_common_words_in_English). In our excerpt from *Peter Pan*, the most common words were only three-characters long. As a result, compressing the text made only a small impact (6%).

### Run-Length Compression

Sometimes a single letter is repeated consecutively many times, such as in `AAAAAAAAAAAAAAAH, A SPIDER!`. With *run-length compression*, we can reduce repeated characters by a single character value and its count (`A15H, A SPIDER!`). 

This can also be helpful for encoding a screenshot of black text on a solid white background. In the image, there will be many long **runs** of white pixels, and very few and short runs of black pixels. To represent the screen, we could encode this into text, where `W` represents a white pixel and `B` represents a black pixel:

`WWWWWWWWWWWWBWWWWWWWWWWWWBBBWWWWWWWWWWWWWWWWWWWWWWWWBWWWWWWWWWWWWWW`

With the run-length compression **algorithm** (an algorithm is just a series of steps to achieve something; the goal in this case is to compress the text), this sequence of `W`s and `B`s can be compressed into `12W1B12W3B24W1B14W` and still mean the same thing. 

### Huffman Coding

The creator of the **Huffman compression algorithm**, Dr. David Huffman asked *Why should the letter `X` or `Q`, which are rarely used, take up the same number of bits as a `space`, which is frequently used?* <br>

<iframe src="https://drive.google.com/file/d/1GX-ehLwxna5RTF7K3GeXvnCJla7DZJqs/preview" width="640" height="480"></iframe>

As a result, the Huffman algorithm uses less bits for common letters, and more bits for uncommon letters. For instance, `E` is a common letter and is represented in the Huffman encoding algorithm by just 3 bits (`000`). On the other hand, `X` is rarely used, so it is represented with more bits (`1111100010`). 

<iframe src="https://drive.google.com/file/d/1dZ4z0ffWwvQZO6vVJDH2W4nn250I6Bsm/preview" width="640" height="480"></iframe>

Above is the **Huffman tree**. Unlike in the natural world, the **root** of the tree is at the very top, and the tree grows downwards on the page. Also, a circle (aka **node**) can split into several paths (aka **branches**). The tree ends with **leaves**. It's helpful to just turn the diagram upside-down and view it as a tree in the real-world. 

This particular tree is called a **binary tree**. This means that every node is either branch with exactly two **children**. This is useful because any path from the root to a leaf corresponds to a binary number. Going **left** from a node is represented by `zero`, and going **right** is represented by `one`. 

For example, the number `01010` really means "start at the root, then go left-right-left-right-left". This lands on the leaf labelled `C`.

<iframe width="650" height="315" src="https://www.youtube.com/embed/JsTptu56GM8?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>