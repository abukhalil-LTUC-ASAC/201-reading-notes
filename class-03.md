# Lists, Boxes and loops

This might be a long list, but here it is anyway. Some more HTML from the book, and some more JS to end with.

## There are 3 types of lists in HTML
You read that correctly. They are:
1. Ordered List that comes numbered.
* Unordered List with bullets or other shapes
<dl><dt>Definition List</dt><dd>That shows definitions just like a dictionary</dd></dl>

## Boxes in CSS

As mentioned yesterday, CSS applies its style as elements in a boxing match. With *higher*(As in parent element) boxes having mostly bigger sizes, and each other box is contained within or next each other.

These boxes are defined with width and height, and it's of importance to keep in note how different screens affect the content and adjust accordingly.

Most used properties in CSS can be compiled into: 
* **Whitespace** adders such as Border, Margin and Padding, each can affect one or all sides of their boxes
* Box **position**, relative to its parent box, or otherwise fixed to the screen's perspective and such.
* How sibling boxes are displayed using **display**, as they can be changed to be displayed as a whole inline block, or both inline and individual block
* **Visibility** changes since they become really handy when coupled with JS [DOM](https://www.w3schools.com/js/js_htmldom.asp) manipulation 
* **Box-shadow** for that sweet, professional look you always wanted. *When used correctly*, along with **border-radius** for rounded corners and **border-image** for the final touches.

There are many more tricks in CSS to make different objects that are not available by default, such as the [frosting glass effect](https://css-tricks.com/frosting-glass-css-filters/) I had learned a week ago that turned boring objects to something really cool.

## What if-then else? switch it.

You might be familiar with these statements, but then wondered why choose one over the other? For me it has been simple, if I want to check a variable against every case, but only use one of them I'd use the switch, else I'd use the if with better nesting options, and the check against all cases even if one is found.

Cases can use mixed data types, making JS a weak typing language that allows flexibility, and still have a strict option of === and ==!. 

Truthy and falsy values are fun to look it, with false equaling `false, 0, '', 10/'score', var highscore;' and truth to be everything else.

Don't forget that cases without operators are called unary, and will only check for it's existence.

There is an interesting case of short circuit values, with logical operators returning a variable if it exists, but will continue to the next operation if it did not. such as:
```
var artist = 'Rembrandt' ;
var artistA = (artist || 'Unknown') ;
```
Where artistA is either artist or unknown, but is artist if it exists, and Unknown otherwise.

<button name="button" onclick="https://abukhalil95.github.io/reading-notes/class-04">Next</button>