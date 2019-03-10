---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Languages and Protocols of the Web
# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   An HTML reference sheet

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

HyperText Transfer Protocol (**HTTP**) lies in the *Presentation* layer of the [OSI Model](https://ramnauth.github.io/bus%20110/2019/03/10/networking/#open-systems--protocols) because HTTP format web data so the user can view it. HTTP is how your web browser requests resources from a web server. There are different actions that happen:
- `GET` - access/download the resource, such as view the webpage
- `POST` - send some data, such as through a webform.
- additional other HTTP request methods  - [link](https://www.tutorialspoint.com/http/http_requests.htm)

HTTP also has response codes for each action/request:
- 200 means “OK” or successful
- 3xx is some sort of “redirect”
- 400 means request was malformed
- 403 means “forbidden”
- 404 means “not found”
- 5xx means server error
- additional status codes - [link](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

HyperText Markup Language (**HTML**) is the language we use to create the content and layout of web pages. We can also include Cascading Style Sheets (CSS) and JavaScript for style and animation.

Reference sheet contents:
- [Basic HTML Structure](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#basic-html-structure)
- [Plain Text Tags](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#plain-text-tags)
- [Text Formatting](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#text-formatting)
- [Lists](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#lists)
- [Images](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#images)
- [Links](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#links)
- [Style](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#style)
- [Special Characters](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#special-characters)
- [iFrames](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#iframes)
- [General Tags](https://ramnauth.github.io/bus%20110/2019/03/10/web-development/#general-tags)

## Basic HTML Structure
```html
<html>
	<!-- a comment --> 
	<head>
		<title> your website title </title>
	</head>
	
	<body>
		<!-- the content of your website goes here -->
	</body>
</html>
```

## Plain Text Tags
```html
<!-- there are only six levels of headings -->
<h1> </h1>  <!-- used for main headings -->
<h2> </h2>  <!-- used for sub headings -->
<h3> </h3>  <!-- used for sub sub headings -->
<h4> </h4>  <!-- used for sub sub sub headings -->
<h5> </h5>  <!-- used for sub sub sub sub  headings -->
<h6> </h6>  <!-- used for sub sub sub sub sub headings -->

<p> your paragraph </p>
```

## Text Formatting
```html
<b> your bold text </b>
<strong> also bold text </strong>

<i> your italicized text </i>
<em> also italicized text </em>

<u> your underlined text </u>

<s> your striked-out text <s> 
<strike> also striked-out text </strike> 

<sup> your superscript text </sup>
<sub> your subscript text </sub>

<small> your small fineprint size text </small>
<tt> your typewriter text <tt>
<blockquote> your indented text block quote </blockquote>

<br /> <!-- starts a new line --> 
<hr /> <!-- draws a horizontal line --> 
```

## Lists
```html
<!-- an ordered (aka numbered) list -->
<ol> 
	<li> A list item </li>
	<li> Another list item </li>
	<li> Another list item </li>
<ol>

<ol type ="A"> ... <ol> <!-- an ordered list using uppercase letters -->
<ol type ="a"> ... <ol> <!-- an ordered list using lowercase letters -->
<ol type ="i"> ... <ol> <!-- an ordered list using roman numerals -->
<ol type ="1"> ... <ol> <!-- an ordered list using numbers -->

<!-- an unordered (aka bulleted) list -->
<ul> 
	<li> A list item </li>
	<li> Another list item </li>
	<li> Another list item </li>
<ul>

<ul type ="disc"> ... <ul> 		<!-- an unordered list using whole circles -->
<ul type ="circle"> ... <ul> 		<!-- an unordered list using hollow circles -->
<ul type ="square"> ... <ul> 		<!-- an unordered list using squares -->
```

## Images
```html
<img src="url"> <!-- the basic image tag -->
 
<!-- <img> tag attributes -->
	src = "url" 			<!-- the URL or filename of the image -->
	alt = "text" 			<!-- the alternate text, if the image doesn't show -->
	width = "size" 			<!-- the image width (in px or %) -->
	height = "size" 		<!-- the image height (in px or %) -->
	border = "thickness" 		<!-- border thickness in px -->
	vspace = "space" 		<!-- the space above/below the image in px -->
	hspace = "space" 		<!-- the space left/right the image in px -->
```

## Links
```html
<a href="url"> link text </a> <!-- the basic link tag -->

<!-- <a> tag attributes -->
	href="url"			<!-- location of the page to link to -->
	name="name" 			<!-- name of the link -->
	target="_self" 			<!-- opens link in current tab -->
	target="_blank" 		<!-- opens link in a new tab -->
	href="mailto:email" 		<!-- link to initiate an email -->
```

## Style

For HTML-supported colors, see [HTML Color Names](https://www.w3schools.com/colors/colors_names.asp)

For HTML-supported fonts, see [Web Safe Fonts](https://www.w3schools.com/cssref/css_websafe_fonts.asp).

```html
<html>
  <head>
    
    <!-- tab icon and title -->
    <link rel="shortcut icon" type="image/png" href="/logo.png"/>
    <title> your page title</title>
    
    <!-- CSS -->
    <style> 
      body {
        font-family: "arial";  					/* change the font */
		background-color: yellow; 			/* change background standard color */
		background-color: #ff3399;			/* change background color using hexcode */
		background-color: rgba(255, 0, 0, 0.2);		/* change background color using red, green, blue, alpha levels */
		line-height: 3px;			/* change spacing between lines */
		font-size: 20px;			/* change font size */
		display: block;				/* nothing can appear on the same line as this object */
		display: inline;			/* objects can appear on the same line */
      }
	  img {
		transform: rotate(20deg)		/* rotate the image 20 degrees */
		transform: skew(20deg)			/* skew the image 20 degrees */
		transform: scaleY(1.5)			/* dilate the image's height by factor of 1.5 */
	  }
	  img:hover {
		/* describe the style of the image when the user hovers over it */ 
	  }
    </style>
  </head>
```

For more information on how to style your HTML tags, see [w3schools CSS tutorials](https://www.w3schools.com/css/default.asp).

## Special Characters
For a list of [ISO codes](http://www.simplehtmlguide.com/isocodes.php).

```html
&lt;			< - Less-Than Symbol
&gt;			> - Greater-Than Symbol
&amp;			& - Ampersand, or 'and' sign
&quot;			" - Quotation Mark
&copy;			© - Copyright Symbol
&trade;			™ - Trademark Symbol
&nbsp;			  - A space (non-breaking space)
&#??;			ISO 8859-1 character - replace ?? with the iso code
```

## iFrames
An iframe is an HTML element that allows an external website to be embedded into your HTML document. 

Some popular sources for iframes:
- Embedding a YouTube video: [tutorial link](https://www.w3schools.com/html/html_youtube.asp)
- Embedding a file in Google Drive: [tutorial link](https://en.support.wordpress.com/google-docs/)
- Embedding an interactive Google Map: [tutorial link](https://www.dummies.com/web-design-development/site-development/how-to-embed-a-google-map-with-iframe/)
- Embedding your repl.it code: click on the `Share` button, then copy the HTML code in `Embed`.

See my repl.it HTML code here: [https://repl.it/@rramnauth2220/intro](https://repl.it/@rramnauth2220/intro) 

Viewing the website right here using an iframe: 
<iframe height="400px" width="100%" src="https://repl.it/@rramnauth2220/intro?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

## General Tags
```html
<!DOCTYPE html ... > 				<!-- Document Type Definition -->
<link />					<!-- link to other content -->

<!-- <link/> tag attributes -->
	rel="relationship" 			<!-- type of relationship to the html document -->
	http="url" 				<!-- URL or file location being linked -->
	type="type"				<!-- type of object or file, eg: text/css -->
	title="link title"			<!-- link title -->
```