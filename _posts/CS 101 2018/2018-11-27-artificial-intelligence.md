---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Artificial Intelligence
# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   We talked a lot about how computers can fetch, interpret, read, and display data, but how do computers make decisions on this data?

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

Think about the *traditional* roles of humans versus those of machines. Machines do the heavy-lifting and manual labor more quickly and accurately.
Humans, on the other hand, control tasks, plan calculations, interpret results, and communicate in a human-understandable way. Now, the roles of machine versus human are blurred. You have [self-driving cars](https://waymo.com/), 
programs that [beat world chess champions](https://en.wikipedia.org/wiki/AlphaZero), and software that [replace diagnosticians](https://www.forbes.com/sites/haroldstark/2017/07/10/prepare-yourselves-robots-will-soon-replace-doctors-in-healthcare/) and other doctors.
From spam filters to self-driving cars, there has been an increasing need for our machines to learn from data and use that knowledge to make predictions and decisions. 
This is the heart of **artificial intelligence** (AI).

## Not-so Intelligent Programs?
Not every program that does something a human could typically do is deemed "intelligent". In general, computer programs that can do human-like tasks are extremely useful in answering questions like
- is an email spam? 
- does this patient's heart have arrythmia?
- will it be raining tomorrow?
- what song should Spotify play next? 

While useful, we don't describe these programs as "intelligent" in the same way we think of **human intelligence**. The main goal of artificial intelligence is, however, to *simulate* human intelligence in machines.

## Goals of AI
Machines that mimic human cognitive functions such as learning and problem solving are considered **intelligent**. The scope of AI is often disputed. Because as machine become increasingly capable, a phenomenon called the **AI effect** kicks in. Critics start saying that intelligence is not just doing what we know humans are already capable of. Instead, intelligence is doing whatever hasn't been done yet ([Tesler's Theorem](https://en.wikipedia.org/wiki/AI_effect)). Nonetheless, the common goals of AI research include:
- **reasoning** such as in [automated proof checking](https://en.wikipedia.org/wiki/Proof_assistant)
- **knowledge representation**, that is representing information about the world and then using that information to do complex tasks (e.g., diagnosing a medical condition)
- **planning**, or strategizing often for autonomous agents (e.g., self-driving cars, unmanned robots)
- **natural language processing**, or understanding, using, and responding to human speech
- **perception**, such as being aware and able to relate to the world around (e.g., facial recognition, computer audition)
- **learning**, famously known as the field of **Machine Learning** (ML) where machines try to improve their performance at a certain task (e.g., playing chess)

## Approaches
Trying to capture human intelligence is a very ambitious task. But there are several popular ways of approaching the problem:
- **cybernetics** is an approach that tries to connect neurobiology and information theory to build machines that used electronic networks similar to our biology. This approach was largely abandoned by 1960, but [Grey Walter's turtles](https://en.wikipedia.org/wiki/Turtle_(robot)) and [John Hopkins Beast](https://en.wikipedia.org/wiki/Johns_Hopkins_Beast) were contributors for its revival in the 1980s.
- **symbolic** AI is based on high-level "symbolic" (aka human-readable) representations of problems. This approach took the baton from cybernetics and continued the research with a slightly different perspective:
	- **cognitive simulation** is the study of simulating human problem-solving skills and techniques
	- **logic-based** instead tries to find the essence of abstract reasoning and problem solving, often using formal logic
	- **anti-logic** (aka **scruffy**) believe that it is impossible to capture all aspects of human-intelligent behavior. It's "messy" or "scruffy" in that anti-logic researchers believe that AI must be built by hand, one complicated concept at a time.
	- **knowledge-based** computers are computers that use a storage of facts and rules relating to the task at hand. A **knowledge revolution** occurs in computer history when we realized that an enormous amount of knowledge would be required to create a truly intelligent application.
- **sub-symbolic** AI research believes that we'll never be able to mimic all aspects of human cognition. Instead, sub-symbolic research tries to approach intelligence without specific representations of knowledge. For example, in **embodied intelligence**, researchers believe that the idea of a body (movement, perception, and visualization) is required for higher intelligence. Also, in **computational intelligence** (aka **soft computing**) neural networks try to simulate our brain in addition to evolutionary computation and lots of statistical methods.
- **statistical learning** has a lot of overlap with the previous fields but is focusing on generalizing real-world results through statistical means. **Data mining** falls under this umbrella approach.

## Tools
Before we capture all of human intelligence, we need to take baby steps. These baby steps become our tools or building blocks. A few AI tools that we covered in class are:
- **search and optimization** We discussed:
	- [Dijsktra's algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) for finding the shortest path
	![Dijsktra shortest path algorithm](https://www.geeksforgeeks.org/wp-content/uploads/Fig-11.jpg)
	- The [Traveling Salesman Problem](https://en.wikipedia.org/wiki/Travelling_salesman_problem#Description)
	- The [Six Frogs Problem](https://liucs.net/cs101f18/a7-ai.html)
	- The [Fox, Goose, & Bag of Beans Puzzle](https://en.wikipedia.org/wiki/Fox,_goose_and_bag_of_beans_puzzle)
	- The [15-puzzle](https://en.wikipedia.org/wiki/15_puzzle) using the [A* search algorithm](https://en.wikipedia.org/wiki/A*_search_algorithm)
- **logic** such as with [decision trees](https://en.wikipedia.org/wiki/Decision_tree) (example below), and [random forests](https://en.wikipedia.org/wiki/Random_forest)
![Decision tree](http://www.doc.ic.ac.uk/~sgc/teaching/pre2012/v231/dt1.gif)
- **probabilistic methods** as demonstrated with [random walkers](https://en.wikipedia.org/wiki/Random_walk) (image below)
![Random Walker](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7c/Random_walk_2500.svg/280px-Random_walk_2500.svg.png)
- **statistical learning methods** such as the [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) and general data clustering
- **neural networks** (example below) and **deep learning**
![Neural Network](https://cdn-images-1.medium.com/max/1200/1*CcQPggEbLgej32mVF2lalg.png)

## Additional Topics & Resources
- [Class Presentation](https://docs.google.com/presentation/d/10c3tCrRZPHeSq9Qlg8ni0HGNmrEKEeqSUqXH4kt4e84/edit?usp=sharing)
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSWZyeJjiRbvwq4gdxseh-864qdh_azxR8hxr_PqOUmPBqGF_Yj9c0x7Bo74PqoDK8TAN30-wYgL1_8/embed?start=false&loop=false&delayms=3000" frameborder="0" width="480" height="299" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
- [CrashCourse #34 Artificial intelligence](https://youtu.be/z-EtmaFJieY)
- [Turing Test](https://en.wikipedia.org/wiki/Turing_test) - on measuring how effective an artificially intelligent machine is.
- [A critique of the Turing Test](https://www.newyorker.com/tech/annals-of-technology/why-cant-my-computer-understand-me), an article titled *Why Can't my Computer Understand Me?* by Gary Marcus