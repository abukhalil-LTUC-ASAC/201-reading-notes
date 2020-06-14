# Tabling your ideas to the web

Structured information is often presented many ways, depending on it's nature! It could be a hierarchy in the case of verbal information or in a formatted table for data driven information. Tables break data down to dimensional parts, mostly in two dimensions using the first column and first row as axes.

The format follows this configuration:
```
<table>
  <tr>
    <th></th>
    <th scope="col">Friday</th>
    <th scope="col">Saturday</th>
    <th scope="col">Sunday</th>
    <th scope="col">Monday</th>
  </tr>
  <tr>
    <th scope="row">Activities</th>
    <td>Gardening</td>
    <td colspan="2">Studying</td>
  </tr>
  <tr>
    <th scope="row">Cash</th>
    <td>20$</td>
    <td colspan="2">0$</td>
  </tr>
</table>
```
<table>
  <tr>
    <th></th>
    <th scope="col">Friday</th>
    <th scope="col">Saturday</th>
    <th scope="col">Sunday</th>
    <th scope="col">Monday</th>
  </tr>
  <tr>
    <th scope="row">Activities</th>
    <td>Gardening</td>
    <td colspan="3">Studying</td>
  </tr>
  <tr>
    <th scope="row">Cash</th>
    <td>20$</td>
    <td colspan="2">0$</td>
    <td>120$</td>
  </tr>
</table>

The example is very sufficient in showing how data `<td>` is inputted, under `<tr>` which defines the rows and encompassed by `<table>` that defines the element. `<th>` helps define our row and column headers. `colspan`,`rowspan` attributes allow cell merging and data to encompass multiple columns. Additional elements were implemented to help resolve issues when tables become large, such as adding `<thead>`,`<tbody>`,`<tfoot>` to define head, body and footer data which helps with css styling a ton.

Important css properties can be applied to individual cells, or applied to the whole table and are defined as:

* width, cellpadding and cellspacing which adds the respective properties to each cell.
* border, bgcolor affects border width and background color of cells.

## Increasing your object understanding

I have had a great deal of trouble doing a past project of mine, dealing with marker objects in a google map API environment. These troubles were mostly about how to access and update these markers dynamically according to inputted json file of information. The following reading will skip the possibility of getting into trouble when doing it again in different context.

The main difference between using the dot operator `shop.name = 'Seattle'` and the bracket syntax `shop['name'] = 'Seattle'` is if you knew the naming of that specific property `name`, empty string will delete the value, and `delete shop.name` will remove the property.

### One Object to rule them all

Getting a function to write objects for you, with only difference in value is a major improvement to just simply copy past fill past objects of similar types. This function is known as an [object constructor](https://www.geeksforgeeks.org/javascript-object-constructors), and it is one of the ways to do major improvement in code quality.
```
function Shop(name, maxCustomers, minCustomers){
  this.name = name;
  this.maxCustomers = maxCustomers;
  this.minCustomers = minCustomers;
  this.method = function(){
    return this.somemethod;
  }
}
```
The way to <dfn title="cause a procedure to be carried out.">invoke</dfn> the constructor process is simple. Just add a new variable: `var Seattle = new Shop('Seattle', 20, 5);`

### Hey! [this.isHard](https://www.freecodecamp.org/news/how-to-understand-the-keyword-this-and-context-in-javascript-cd624c6b74b8/)

But it can be understood! Just apply the keyword and replace it within context, Ha.
There are common ways to think about it, depending on the object's context.
* Global, as in `<script>` level objects, this.property always refers to the object it is contained in.
* Functions as methods in objects, it only refers to the object parent, or the constructor object, for each object created.

### Arrays in objects, and objects in arrays

Both can be interchange to accommodate complex data structures, these are often used when you have to hold multiple objects in an array, or hold property values as array of multiple indexes for different conditions.

## Reading Web Pages like the palm of your hand

There are proven steps to make sure you'd understand any given problem domain and example applications of web apps. These include understanding the three domains that each browser has in common, and they are all about built-in objects.

* Browser Object Model: These objects define browser level objects such as tabs, screen size and browser history.
  - Window with properties(screen, innerHeight) and methods (alert(), open(), print()).
* Document Object Model: As learned before, the document object serves as a gateway for all objects inside a web document.
  - Document with properties (title, URL, domain) and methods (write(),getElementById()).
* Global Javascript Objects: Which represents all objects that javascript frequently uses to execute various functionalities.
  - Javascript (String, Math, Date) with properties (length, PI) and methods (isNan(), getDate(), round())

With the rest coming out of lookup and practice. Familiarity can only get you so far.