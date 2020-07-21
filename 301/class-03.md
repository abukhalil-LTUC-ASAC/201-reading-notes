# Don't repeat yourself with Templating, and help the frogs with Flexboxfroggy.

Be efficient, and win over internet users too using [**Javascript Templating**](https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2)

## [The Best Mustache Ever](https://github.com/janl/mustache.js)

It is really more about how it moves around, than how it looks at first but both are equally important! So the template gets your data in the Javascript JSON format and renders them into HTML tags with variables filled in.

An absolute machine, with no logics what so ever, [this beast](https://mustache.github.io/mustache.5.html) operates by getting the values from json, and expands the template accordingly.

To get started, add the following command `$ npm install mustache --save` then the following JS lines:
<img src="https://miro.medium.com/max/875/1*ES10lxr7tdRFVEKcRAgLEw.png" width="600">

Using it follow the general rule: `res.render('hello', {"name": "Yahya"})` with hello specifying the name of the html document, and `"name"` replacing the placeholder {{name}} inside of `hello.html` which we can get using JSON or as a variable `var nameObject = {"name": "Yahya"}`. 

## [Leaping to safety](https://flexboxfroggy.com/) with flexboxes

There is no way to describe how these works better than playing [*the game*]((https://flexboxfroggy.com/)), [the guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) offers comprehensive review if you ever forgot about them.

Flexboxfroggy explains the following in this order:

* `justify-content:` horizontal displacement and `space-between/around`.
* `align-items:` for vertical displacement and `stretch`.
* `flex-direction:` `row/-reverse`, `column/-reverse` for respective direction flow.
* `order: int` to change its relative position among siblings by int.
* `align-self:` for individual displacement with same input as align-items.
* `flex-wrap:` to either squeeze everything inside a single line with `nowrap` or `wrap/-reverse` for multiple lines.
* `flex-flow:` combines `flex-direction` and `flex-wrap` with input separated by spaces `flex-flow: column wrap`.
* `align-content: flex-start` looks similar to `align-items` but is more about the spaces between the content and tries to fit it all as needed.

visually inside a container are more options to control each flex item. 
* `flex-grow: 4;` & `flex-shrink: 3;` defines that that item should take up 4 more times or 3 less times of space relative to other items inside its parent, if they were all defined with `flex-grow: 1;` or as default.
* `flex-basis: |auto` helps define the basis of grow or shrink, if its zero it wont be affected.

Shorthand for the three is: 
```
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```
It is time to start flexing, amirite?