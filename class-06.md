# Object Oriented Programming - Basics

Starting from today, we will work our way to understand what objects mean, in OOP standards.

## First, there is the creation

The format: 
```
var house = {
  owner: 'David',
  bedrooms: '3',
  bathrooms: '2',
  garden: yes,
  costYearly: 6,000.00,
  floors: '2',
  houseTypes: ['Apartment', 'withRoof'],
  NumberOfRooms: function() {
    return this.bedrooms * this.bathrooms
  }
}
```
This does look very similar to the normal javascript function declaration. But instead the function is an object, with variables named as properties and are declared by `:` and has inner functions that are called methods. Each property is called key(Unique), and is defined by value. Methods use properties and other inputs to construct other values.

Most important reasons to using objects is to reuse the general structure over multiple cases, and never have to rewrite full variable declarations and functions over and over for different cases such as [this.example](https://stackoverflow.com/questions/6930601/why-how-should-i-used-objects-in-javascript).

Other interesting fact is you could access values of object properties and using their methods using a dot operator `var houseOwner = house.owner;` or `var houseOwner = house['owner']` and flipping it will assign a value to that property `house['owner'] = Yazeed`

## Then the website became as it is

With its **Document**, **Element**, **Attribute** and **Text** Nodes, that each web page has a model of to translate the information to our pages that we see. Javascript interacts with such nodes and changes them dynamically, allowing for interactive web apps to happen!

![DOM picture](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1024px-DOM-model.svg.png)

You start with the **document** node, which encompasses the whole web page, then work down to **elements** such as `<div>` which has **property** nodes attached, all the way to **text** nodes which are our end points.

Interesting things to learn are how to access each element, by selecting it:
* Individual:
  * getElementByld() which are defined by ID
  * querySelector() uses css selectors and picks first
* Multiple:
  * getElementsByClassName() which are defined by class
  * getElementsByTagName() which are defined by tag
  * querySelectorAll() uses css selectors and picks all
* Relational:
  * parentNode
  * previous/nextSibling
  * first/lastChild

And even more interesting work comes with doing actual work in their values. These works can be simplified as `nodeValue` to access node content but not text or child. Changes to text and inner child content happens with `innerHTML` or `textContent` for text only.

New nodes can be created or old can be removed using `createElement()`, `createTextNode()`, `append/removeChild` as DOM manipulators. Their properties are accessed and changed using `hasAttribute()`, `getAttribute()`, `setAttribute()`, `removeAttribute()` which affect id's and classes.

**DOM queries** means finding elements, and saving that element in a variable actually saves its location for further manipulations. CSS selector queries will be most used as it is very specific and handy when doing very fine manipulations on the DOM tree. Extra effort into the selectors are needed for frontend development.


