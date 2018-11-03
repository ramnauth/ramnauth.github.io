---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Rules for Pair Programming

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Pair programming is very powerful but too often misunderstood. Here are some rules & techniques for pair programming.

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
tags: [Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

Pair programming is a term that comes from [agile software development](https://en.wikipedia.org/wiki/Agile_software_development) and describes a technique in which two programmers collaborate at one workstation/computer. One programmer, the *driver*, writes code while the other, the *navigator*, reviews each line of code as it is typed.
From Robert Kessler and Laurie Williams' [Pair Programming Illuminated](https://www.amazon.com/Pair-Programming-Illuminated-Laurie-Williams/dp/0201745763/ref=sr_1_1?s=books&ie=UTF8&qid=1541282608&sr=1-1&keywords=pair+programming+illuminated), here are some tips to keep in mind.

## 7 Synergistic Behaviors
Always aim to get the most out of these seven behaviors:
1. **Pair Pressure** is not wanting to let your partner down plus the satisfaction of working harder (and smarter) than you would alone
2. **Pair Negotiation** is about combining two minds on design and implementation to yield the best possible solution
3. **Pair Courage** states that you are more likely to take on challenging tasks than you would have alone
4. **Pair Review** is the continuous review of design/implementation
5. **Pair Debugging** allows us to identify a problem more quickly and enjoyably
6. **Pair Learning** is improving or acquiring skills from a fellow programmer
7. **Pair Trust** is becoming more confident in each other's skills and communication because you are supported

## Games

### Ping Pong
1. Driver attempts to complete a single aspect of the project (that is, writes a single function, creates a test class, writes an initially failing test, etc.)
2. Switch roles
3. New driver fixes a previous error or completes a new single aspect of the project
4. Pair negotiates [refactoring](https://en.wikipedia.org/wiki/Code_refactoring), [prettifying](https://ramnauth.github.io/cs%20102/2018/09/26/style/), or other areas of design and implementation
5. Rinse and repeat until the project is complete

**Uses:** Ping Pong is great for test-driven development/projects.

### Beat the Clock
1. Get a physical or virtual timer/stopwatch
2. Decide who will be the first driver
3. Set the timer and let the driver get as far as he/she can with the navigator's help
4. When time is up, switch roles
5. Rinse and repeat until the project is complete.

**Uses:** Beat the Clock is great for enforcing pace and limiting keyboard hogs

### Freeform
1. Either programmer starts driving
2. Switch roles as needs
3. Maintain synergistic behaviors
4. Rinse and repeat until project is complete.

**Uses:** Freeform is great for advanced pairing practitioners or pairs that already have had experience programming together

## Dialogue
Consider the 4 "C"s of Pairing Dialogue:
1. **Communication:** do you agree that you both are communicating well with each other?
2. **Comfort:** do you both feel comfortable in the context you're working?
3. **Confidence:** are you both confident in your skills and your team-mate's? If not, have you voiced your fears?
4. **Compromise:** are you willing to make compromises to make progress? 

Alongside the 4 "C"s, consider the following tips to phrasing your sentences:
- Say **"I think..."** to propose an idea.
- Ask **"Do we agree...?"** to confirm agreement.
- Say **"We agree that..."** to discuss your current progress towards goals
- Avoid **"No, but..."** and try saying **"Yes and..."**
- Avoid "You..." statements and try using **"I..."** statements
- Never apologize for your ideas
- **"Please"** and **"Thank you"** are still (and will always be) magic words

## Etiquette
1. Turn on the line numbers in your IDE or text editor if available. This makes it easier for you and your partner to reference to sections/lines of code in your discussions.
2. Ask for the mouse or keyboard. Don't fight.
3. Remember to point with your mouse. Avoid fingerprints and pencil marks on your monitors.
4. Use paper to express/explain your ideas further. 
5. Document your steps, progress, bugs, and solutions.
