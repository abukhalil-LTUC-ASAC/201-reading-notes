# Your Introduction into Efficiency 

One of the more fascinating things, when graduating from pure javascript and entering the world of libraries such as JQuery and frameworks such as react, is how much more efficient the work can become. And it is not just about having to write less code, but also get the code into your head faster and parse through the whole code since it is more compact and more [declarative](https://en.wikipedia.org/wiki/Declarative_programming) that is straightforward with each step onward.

## JQuery

When writing JQuery, you'd notice a couple of thing, at least I did, that is selectors are much more powerful, since it also involve css selectors inside JS context. Tasks are aso much more compact using predefined methods, along with event handling that used to take multiple lines of nonsense and not to speak about the saved fallback code.

The selection starts with either what you'd normally by using `id` or `class`, or use the CSS selectors such as `li:lt(3)` that would select the third list item, then attach event listeners and finally add your actions, single or chained with `.` dot operator. 
```
$('li').on('click', function() {
$(this) . remove();}
```
[All Jquery Selectors](https://api.jquery.com/category/selectors/)

Some caveats: 
* Getting and setting information using the same method might not apply to all elements selected. Especially when you'd try to get information of multiple elements, of which a traverse dom method is needed.
* Caching the selection is a must, if it will be used multiple times to make for efficient storage. If you are wondering what that means, it simple means to `var mySelection = $('li:lt(3));`
* Implicit iteration saves lots of headache in declaring loops. Make use of JQuery methods to do that.
* And of course, chains: `$('li[id!="one"]').hide().delay(5OO).fadeln(1400);`
* Use `$(document).ready` method, but if you already call the script at the end of the html document, [you might not need to.](https://stackoverflow.com/questions/1438883/jquery-why-use-document-ready-if-external-js-at-bottom-of-page).

Another interesting case is in manipulating CSS attributes using `.css()` method, and in between the brackets is your attributes.

Event handlers has quite the functionality, using only `.on( events[,selector][,dataContent: "datahere"], function(e));` line of code. You could notice what it offers, `selector` is another subset of the original selection before `.on`. Additional `dataContent` is sent through `e.data.dataContent` along with the `e` event object.

So start it up using 
```
<script src =" // ajax .googl eapi s . com / ajax /l i bs/ jquery / 1.10 . 2/ jquery .min. js ">
</ script>

< script>
window .jQuery 11 document. write (' < script src =" j s/j query- 1.10 . 2 .j s
11 ><\jscri pt> ')
</ script>
```
 The fallback is required if cdn is unavailable due to ban on certain website or if it is down.


## Pair Programming

What we have learned from past 201, is to fully utilize the opportunity to check how others thought processes happen in a work environment. It has been insightful in seeing how unique mini-hacks each person tend to use to make life a bit easier.

What does code fellows tell us about pair programming, that we could derive from experience and make sense of?

* Greater efficiency, a true hacker of life by making use of new techniques to implement in work. It takes a while however, to make sense of each other's thoughts and make the process as smooth as possible/

* Engaged collaboration, as in procrastination killer as it would be hard or embarrassing to steer off while the other is looking over the shoulders.

* Learning from fellow students, Most importantly the know how's of problem solving is usually transferred.

* Social skills, by fostering malleable frameworks and  accurate expectations, its easier to deal with diverse range of people with each subsequent work experience that has some element of pair programming in contrast of solo players.

* Job interview readiness, since pair programming is an exercise of information flow, it gets much easier to talk your ideas through to others and especially to recruiters who would do pair programming too sometimes.

* Work environment readiness as a final goal of getting products launched on the get go after graduation.

