---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: A3 - Your Company's Website, due Wed Mar. 27

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   **Assigned** Thurs, Mar. 7, 2019; **Final Due Date:** Thurs, Mar. 27 @ 23:59 PM via [submission portal](https://goo.gl/forms/ekqNXkCALpIRfo5T2); Handout: [PDF](https://drive.google.com/file/d/1JwhXHxp3Z6Rjwg3zMz4OGyul6hW-TkhD/view?usp=sharing)

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
categories: [BUS 110]
tags: []
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

See assignment handout ([link](https://drive.google.com/file/d/1JwhXHxp3Z6Rjwg3zMz4OGyul6hW-TkhD/view?usp=sharing)) for complete instructions and examples.

**Overview**: In this assignment, you will write a ‘About this Business’ web page using HTML and CSS. Complete this assignment in [repl.it](https://repl.it/) and submit the hyperlink via the submission portal. 

## Requirements
Your website must have:
1. The name of your company
2. Your company’s mission statement (1-2 sentences describing what your company does)
3. A list (ordered or unordered) of the services/goods your company provides
4. At least 3 relevant images
5. At least 3 hyperlinks to relevant sources
6. At least one appropriate iframe (e.g., a Google Maps, Google Drive presentation/file, a YouTube video)
7. An ‘About Me’ section containing:
    - Your name
    - Your role at this company (e.g., founder or CTO)
    - Your email address using an `<a href="mailto:youremail@email.com"> email here </a>` tag
    - A brief (1-2 sentences) background/description about yourself

## Submission Portal
Submit your repl.it link here: [https://goo.gl/forms/ekqNXkCALpIRfo5T2](https://goo.gl/forms/ekqNXkCALpIRfo5T2)

## In-Class Example
The following code for the website we built together in class: [https://testnetworking--rramnauth2220.repl.co/](https://testnetworking--rramnauth2220.repl.co/)
```html
<!DOCTYPE html> <!-- document type --> 
<html>
  <head> 
    <title> Musical Lesson Plans </title>
    <link rel="icon" href="https://cdn2.iconfinder.com/data/icons/freecns-cumulus/16/519586-083_Music-512.png" >
    <link href="https://fonts.googleapis.com/css?family=Overpass" rel="stylesheet">
    <style>
      body {
        font-family: "Overpass";
      }
      h1 {
        font-size: 125px;    
        margin: 2px;
      }
      p {
        font-size: 30px;
      }
      a {
        color: #00ffcc;
        background-color: #000000;
        text-decoration: none;
        padding: 10px;
      }
      a:hover {
        background-color: #00ffcc;
        color: #000000;
      }
      li {
        font-size: 30px;
        margin: 20px;
      }
      #contact {
        background-image: url("https://www.designyourway.net/blog/wp-content/uploads/2018/06/Seamless-Space-Pattern-by-J.jpg");
        padding: 30px;
      }
      #end {
        background-color: white;
        color: black;
        padding: 15px;
      }
      #team{
        width: 80%;
        margin-left: 50px;
      }
    </style>
  </head>
  <body> <!-- main content -->
    <h1> Musical Lesson Plans </h1>
    <p> Materials for teaching core subjects through music. Submit your ideas by <a href="#end"> reaching out to us</a>. </p>
    <ol>
      <li> Teaching Programming using <a target="_blank" href="https://youtu.be/Smu5Tio-5MY">Baby Shark</a>
      </li>
      <li>Intro to Physics -- DIY <a href="https://youtu.be/IZGWkCR7T6E">Paper Circuit Tutorial</a>
      </li>
      <li> Intro to Robotics -- DIY <a href="https://youtu.be/6VqS8c_eC0U">Wall-E</a>
      </li>
    </ol>
    <figure>
      <img src="http://news.lib.uchicago.edu/wp-content/uploads/2013/09/CrerarComputerLab-byJasonSmith-1502_ns.jpg" alt="Creative Computer Labs">
      <figcaption> Long Island University Creative Computing Lab </br>
      Picture credits: Rebecca Ramnauth, Class 2017 </figcaption>
    </figure>

    <div id="contact">
      <section id="end">
        <h1> Contact Us </h1> 
        <table>
          <tr> 
            <td>
              <p> We're looking forward to hearing from you! </p>
              <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1427.723129014119!2d-73.98145624306797!3d40.69071140298803!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c25bb33075cf55%3A0x967e6914b74366a4!2sLong+Island+University+Brooklyn!5e0!3m2!1sen!2sus!4v1551973775201" width="600" height="450" frameborder="0" style="border:0" allowfullscreen></iframe>
            </td>
            <td>
              <ul type="square"> 
                <li> <strong> Email: </strong> <a href="mailto:rebecca.ramnauth@my.liu.edu"> rebecca.ramnauth@my.liu.edu </a> </li>
                <li> <strong> Phone: </strong> (718) 488 1000 Ext. 123 </li>
                <li> <strong> Contact: </strong> Prof. Rebecca Ramnauth </li>
              </ul>
              <img id="team" src="https://worklogichr.com/sites/default/files/comm.jpeg" alt="team members">
            </td>
          </tr>
        </table>
        <section>
    </div>
  </body>
</html>
```