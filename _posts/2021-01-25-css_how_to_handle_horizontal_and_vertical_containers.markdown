---
layout: post
title:      "CSS: How to Handle _horizontal_ and _vertical_ Containers"
date:       2021-01-26 03:23:20 +0000
permalink:  css_how_to_handle_horizontal_and_vertical_containers
---


I find myself nearing the end of a build and I reach the point where I want to take a break from puzzling logic and make my work look better than plain HTML formatting. In a lot of my earlier projects, I found myself at the end coding CSS in a. very granular way. I had little method or plan to approach the website formatting, which of course led me to some interesting code in my .css files. 

What happened over and over was that I would have to add effects almost piece meal because my class name and id syntax carried little power. The class names would merely get me access to an individual HTML element. 

My code would get bigger and I would design another page, and soon notice I was have to type simple css commands on multple css code blocks like below.

```

.production-card h2 {
  font-family: 'Big Shoulders Display', sans-serif;
  font-weight: 500;
  font-size: 30px;
}

.title-marquee {
  font-size: 200px;
	
}

.production-header {
  font-family: 'Big Shoulders Display', sans-serif;
  font-weight: 500;
	backround-color: "red";
  border-left: 5px solid magenta;
  border-bottom: 5px solid maroon;

.production-card {
  padding-bottom: 10px;
  margin-right: 15px;
  width: 300px;
	backround-color: "red";
  border-left: 5px solid magenta;
  border-bottom: 5px solid maroon;
	
.member-info {
  padding-left: 10px;
  padding-bottom: 10px;
  margin-right: 15px;
  width: 300px;
  border-left: 5px solid magenta;
  border-bottom: 5px solid maroon;

}
```

Instead of attaching CSS  styling affects to elements, think of CSS styles you may need to apply throughout the website design. Here is a few that I usually consider for every web application:

1. Horizontal layout
1. Vertical layout
1. Any text emphasizing
1. Buttons
1. Links
1. Labels

The two I will discuss are horizontal and vertical layouts.

## Horizontal Layout
The horizontal layouts are useful because often times websites are built with <div> elements, or other block elements. By default, these elements are aligned vertically on top of each other. In your general CSS file, simply add the following code:

```
.horizontal {
display: flex;
flex-direction: row;
flex-wrap: wrap;
}
```

Now, in any parent which contains several div elements, add the class "horizontal" to arrange the children in a row. With the CSS styling above, resizing the window and appending children to the parent will appear in a nicer grid as opposed to a long list of <div> elements.

## Vertical Layout
The vertical layout is useful for similar, quick adjustments to web applications using CSS classes. I use this one the most when I format <form> elements and want the labels and inputs to align vertically. Similar to the horizontal layout, we just add the following code to the CSS file.

```
.vertical {
display: flex;
flex-direction: column;
flex-wrap: wrap;
}
```

Now, by just simply adding the class of "vertical" to any form element, or parent element that needs to align its children vertically, or in the direction of a column.

Check out more _flex box_ styling for enhancing custom layouts.
