# [WATER THAT GARDEN, Solider!](https://cssgridgarden.com/)

What I have learned and what you should too about CSS Grids: 

* `grid-column-start/end: 5;` defines the starting/ending column, not exactly intuitive as ending could be lower than the start, and would move in the reverse, and accepts negative values. Add `span 4` (*only positive*) to allow it to fill 4 columns width. `grid-column` is a shorthand, and accepts both values start then end.

* `grid-row-start/end` is the vertical displacement property, along with the goodies such as `grid-row` and `span 2` property and value.

* Guess what comes after width and height, that's right its ***AREA*** `grid-area: 1 / 1 / 3 / 6;` the shorthand of all shorthands. It is defined as the following ``grid-area: {row-start} / {column-start} / {row-end} / {column-end};`

* Similarly, `order` exists to move the selected element.

* Grid generation, with its default width and height can be specified with `grid-template-columns/rows: repeat(5, 20%);` where `repeat` is the amount of columns/rows and its width. The shorthand is `grid-template: 50% 50% / 200px;` and the template can be used with the following inputs and their combinations: 
  - length
  - percentage
  - flex
  - max/min-content or minmax(min,max);


Another unit is `fr` that specifies the division of space with `1fr` and `6fr` space is divided to 7 equal spaces and is distributed accordingly. `grid-template-columns: 50px 1fr 1fr 1fr 50px` causes both side columns to take up 50px only, and the rest in the middle to be divided equally between 3 columns.

In cssgridgarden, `grid-template: 1fr 50px /20% 1fr;` gets your grid into two columns and two rows, a column that is 20% and the rest is water for the carrots, and a row that fills everything up to last 50px which is poison for the weed!
[**Additional functionalities**](https://css-tricks.com/snippets/css/complete-guide-grid/) available in the complete guide.

## To get started.. 
check this out `grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));`
Autofill would try to fit in as much columns as possible, with a minimum width of 250px and a maximum of 1fr where other elements could fit in nicely.
`grid-gap`, `column-gap` and `row-gap` is what we would call the gutters, or space between the columns and rows if needed.

Responsive examples are further investigated in [this link](https://medium.com/samsung-internet-dev/common-responsive-layouts-with-css-grid-and-some-without-245a862f48df).

## Regex? 

Seems from a skim, a methodology to follow in order to extract information. Sounds useful for my web scrapping app.
Content to check: 
* https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285
* https://regex101.com/
* https://regexr.com/
