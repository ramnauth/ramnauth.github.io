---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Color & Image Encoding

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   How does a computer understand digital images?

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
Binary is the only 'language' computers speaks. Therefore, if we want to represent [numbers](https://ramnauth.github.io/cs%20101/2018/09/10/numbers/), [letters, words, text](https://ramnauth.github.io/cs%20101/2018/09/18/text-encoding/), and images, we must first convert it into binary (`0`s and `1`s).

To store an image on a computer, the image is broken down into tiny *picture elements* called **pixels**. An image with a **resolution** of `11 by 7` pixels has `11` times `7` or `77` pixels. An image composed of just 77 pixels is shown below. Resolution can also refer to the **density** of the pixels in the display, where the unit of measurement is **pixels per inch** (PPI). Given a screen of 250 pixels across 5 inches, the density of pixels is `250 / 5` which is 50 PPI.

![Pixelated Picture](https://i.stack.imgur.com/eaP0f.jpg)

The concept of a pixel is similar to a dot in the art form pointillism. The only difference is, however, pixels fit neatly in a grid. 

![Pointillism Beach](https://docs.google.com/uc?id=1yaH2TGDus7vvDzwenAbyWRNTuuO0dYh9)

![Pixelated Beach](https://docs.google.com/uc?id=1AQ-jz5Sc8-5zxo9NVbouDxfvOLmpKCvB)

## Monochrome (Two-Color) Images

How can we encode pixels as bits (aka *binary digits*)? The simplest scenario is when we're given an image in just black and white. Another way of thinking of a black and white digital image is a grid of pixels that are either `on` or `off`. Then, we can represent each pixel as exactly one bit (either `1` = on = black or `0` = off = white).

![Converting A](https://docs.google.com/uc?id=1g0pjiFw3eeVoDBsJ97ccpQoDLiA4Y1SK)

![Converting B](https://docs.google.com/uc?id=1dfS0_4I3gEBQVbWbG7v4lRZRTmP49ZTa)

![Converting C](https://docs.google.com/uc?id=1JAqM_r8jKPAP-RY5crJibkelyzM_NAlz)

### Exercise 1

![Converting D](https://docs.google.com/uc?id=14pXy2OlYi0Mxb2PdHcu2WTgnthsNrWLp)

We can extend this to grids of more pixels. Below are a few examples on how we can convert 8 x 8 digital images into binary.

![Converting Alien 1](https://docs.google.com/uc?id=1KTFbMPDyAKiI6XyHDtLB4h08lxXcPoUC)

![Converting Alien 2](https://docs.google.com/uc?id=1YxPlonset8iU-QYf2hIr99KfiGVZ83a4)

### Exercise 2

![Converting Alien 3](https://docs.google.com/uc?id=17_q06YFn14xZvVTtksa4iX9pq-Jk0nTG)

### Exercise 3

Can you do this in reverse? Instead of determining the bits from the digital image, can you determine/draw the image if given the bits? 
Draw the image that corresponds to each of the following hexadecimal numbers.

For example, if given the string of hexadecimal digits `3C66703C0E663C00`, you can translate each group of 4 pixels into 1 hex digit.

![Converting Alien 4](https://docs.google.com/uc?id=1Ng3Elg-9DdYiXJrQ5ansE3P4Lq5sE0AH)

Decode the image from these hexadecimal numbers:
- `0066ACD8366ACC00`
- `7E607C0606663C00`
- `C6CCD8F0D8CCC600`

### Exercise 4

Write a 5-letter word in a 8 x 8 pixelated font. For example:

![Pixel Alphabet](https://ct.mob0.com/Fonts/CharacterMap/pixel.png)

Then, translate each letter into binary, and then into hexadecimal. In class, you will challenge your partner to decode the hexadecimal digits to read the word. **Come prepared with your hex digits and grid paper**.

## Color

Before we start exploring how we can combine multiple colors in the same image, let's first explore what color is.

**Color** refers to the wavelength of light. Light of short wave lengths are perceived as violet (a kind of bluish-purple), and the long wavelengths are perceived as red. 
In between these is the usual spectrum of colors: oranges, yellows, greens, blues, and purples. 

![Electromagnetic Waves](https://i.pinimg.com/originals/ed/e7/03/ede703d21f8fb9f291052e37a775d545.jpg)

As shown, color (aka **visible light**) is a very small section of the **electromagnetic spectrum**. However, there are other wavelengths that we can't perceive at all.

From a biological stance, the anatomy of our eyes leads to another explanation of how we see color. Your retina contains detail-sensitive neurons called **rods** (`r` for *resolution*) and color-sensitive neurons called **cones** (`c` for *color*). 
The rods are generally color-blind, whereas the cones come in three flavors: **L**ong-wavelength (red), **M**edium-wavelength (green), and **S**hort-wavelength (blue).

![Cone Types](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Cones_SMJ2_E.svg/375px-Cones_SMJ2_E.svg.png)

Mixing colors of light (an [additive model](https://en.wikipedia.org/wiki/Additive_color)) is different from mixing colors of paint (a [subtractive model](https://en.wikipedia.org/wiki/Subtractive_color)). 

![RGB](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c2/AdditiveColor.svg/330px-AdditiveColor.svg.png)

You can try mixing the primary colors of light (`R` = red, `G` = green, `B` = blue) using Prof. League's RGB demo: [https://contrapunctus.net/rgb-demo/4bit.html](https://contrapunctus.net/rgb-demo/4bit.html)

## Color Encoding

With the idea of mixing red, green, and blue to make any color, it is clear that we need more bits to represent how much of each. When we were converting monochrome (black and white) images into binary, we only needed 1 bit. 
With 2 bits, we can represent four numbers (`0`, `1`, `2`, and `3`) and, therefore, four colors. With 3 bits, we can represent the numbers `0` to `7` (8 numbers, 8 colors). 

Let's use 3 bits, where one bit represents red, another bit represents green, and the last bit represents blue.  

- `0` = `000` = ~~red~~ + ~~green~~ + ~~blue~~ = black
- `1` = `001` = ~~red~~ + ~~green~~ + blue = blue
- `2` = `010` = ~~red~~ + green + ~~blue~~ = green
- `3` = `011` = ~~red~~ + green + blue = cyan
- `4` = `100` = red + ~~green~~ + ~~blue~~ = red
- `5` = `101` = red + ~~green~~ + blue = magenta
- `6` = `110` = red + green + ~~blue~~ = yellow
- `7` = `111` = red + green + blue = white

From black and white images, we can now represent six more colors. However, to make realistic (**true-color**) digital images, we need a lot more color options. To have more colors, we need more bits. 

Today, we typically use 24 bits to represent color. The intensity of red uses 8 bits, green's intensity uses 8 bits, and blue's intensity uses 8 bits. This makes a total of 24 bits.

Because each primary color gets 8 bits, it can also be represented as 2 hexadecimal digits.

![Binary - Hex](https://docs.google.com/uc?id=1ts-nZt-t4dXz29kRubJntdyPJP4krIrI)

You see how the hexadecimal true colors change by adjusting slider in Prof. League's 24-bit color demo: [https://contrapunctus.net/rgb-demo/index.html](https://contrapunctus.net/rgb-demo/index.html)

To practice visualizing colors when given only the hexadecimal number, play the color guessing game [What the Hex](http://yizzle.com/whatthehex/).