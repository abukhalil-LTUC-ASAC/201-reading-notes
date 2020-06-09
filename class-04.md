# Travelling by URL, through a neat structure, with an another.

## Your means of transport.
Links, lots of links are going to be traversed, wether [abroad(Absolute URLS) or locally(Relative URLS)](https://docs.microsoft.com/en-us/sql/ado/guide/data/absolute-and-relative-urls?view=sql-server-ver15). And especially in your grand website, links are going to be a great way to organize the project files through containerization, with the exception of one page web apps, and content manager apps that uses and edits a single template. *Haks..I'd say*

Relative links are defined, according to the page's location from your current page on the project folder. Travelling from Two level deep folders to your index homepage(grandparent) could look like: 
```
<a href="../../index.html"> Home </a>
```
While you have to define the full path when going the other way.
```
<a href="movies/dvd/reviews.html">
```
Mailto: links are a direct way to open an email draft and send to your src URL.
Useful hacks include target="_blank" property in the anchor tag `<a>`, moving to other parts of the same page by adding a unique `src=#tag` and even to another website `src="wiki.com/#footer`.

## The view around you.
It might look messy, but it does not have to! A quick use of [Bootst..](https://getbootstrap.com/docs/4.5/examples/), Ehm proper practices in HTML containerization! You could delay the inevitable bloodbath as a result of a bad boxing career. Understanding Block, and Inline elements is key! As blocks have to take a new line whenever they exist, but inlines are small, coarse and wiggle around everywhere in your HTML and might cause Havoc if not properly supervised.

### Positions
* Normal    |   Default, New line for each element.
* Relative  |   Allows for position change, but without affecting anything else.
* Absolute  |   Elements are pinned relative to the screen with no effect to its neighbors. 
* Fixed     |   These are pinned to the website instead, and has no effect and is not affected either.
* Float     |   Elements float around the target around its position.

Overlapping elements can have a view priority using z-index, which higher elements are viewed first.
With floats, comes chaos, so [clear](https://www.w3schools.com/cssref/pr_class_clear.asp) it, and use borders for its parent to [avoid the great collapse](https://css-tricks.com/all-about-floats/#the-great-collapse)

To make use of neat columns inside a page, float it together, avoid overlapping and specify a reasonable width. As such with the three column css:
```
.column1of3, .column2of3, .column3of3 {
width: 300px;
float: left;
margin: 10px;}
```
### Is it solid, or liquid?
Most important part of defining positions, is because of the variable size of user-interface(screen size), and with such great variability, comes even greater headaches. I'd just go with CSS grids, or other frameworks *ehm..[Bootstrap](https://getbootstrap.com/docs/4.5/examples/)ehm..*. for now.

## An Article on Co-Op programming

Sound like a multiplayer game amirite? Apparently it is quite an experience to have work done in pairs, and it might look exhausting but [experience has shown otherwise](https://www.codefellows.org/blog/6-reasons-for-pair-programming/). Improvement in social skills, work environment readiness seems like a good deal, in comparison to an otherwise solitary work most programmers usually deal with.

## Back to Javascripting 

As seen in an iteration of 201 project, scripting inside a single page might get really confusing, from traversing code flow, the amount of code to readd through at once, together with the general aesthetic it is simply unacceptable and does not properly uses object oriented programming. 

using functions is the way to go, by storing your hundred lines of code inside multiple functions, you could instead follow through 5 lines, each are executed line by line. It starts as:
```
function doThis(input1,input2,..){
    DoingThis;
    DoingThat;
    return something if needed;
}
```
And when you need it, simply call `doThis(input1,input2,..);`, other ways to write functions such as Anonymous(unnamed), and Immediately Invoked Function Expressions (llFE) are mostly used to execute functions once such as events, and arguments. Variable conflicts is a major concern, since normal declared functions share variable names among each other, so one variable exists somewhere, but can be accessed everywhere.