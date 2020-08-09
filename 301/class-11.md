# The EJS aka Javascript Mustache for Express/Node JS


## [Working with EJS](https://ejs.co/)
> What is the "E" for? "Embedded?" Could be. How about "Effective," "Elegant," or just "Easy"? EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. No religiousness about how to organize things. No reinvention of iteration and control-flow. It's just plain JavaScript.


### Getting started with npm
Include npm install ejs

### [**The Basics** *click me for the video*](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt)
Add a line in server.js for `app.set('view engine', 'ejs')`, then you would be able to render files in the `.ejs` format as a response such as `response.render('index')`. 

The parameters of `render` method are split into three parts, `string` which is the file name to render, `object` as an object of which properties you would like to pass into the view file as a variable. And finally is the usual callback parameter we discussed in the previous CallStack topic. What it looks like:

```
response.render('index', {
  foo: 'bar',
})
```

`<%= foo %>` is your view variable which would render as `bar`.

### Additional basics **for loops**
Looping in EJS is as simple as before, by passing an array of objects into the second parameter of render such as:

```
response.render('index', {
  people: [
    { name: Dave },
    { name: Said },
    { name: Mohd }
    ]
})
```

and adding the following lines into the view will simply work.

```
<ul>
  <% for(var person of people) { %>
  <li><%= person.name%></li>
  <% } %>
</ul>
```

### Additional basics **if else**
Add these:

```
<ul>
  <% for(var person of people) { %>
    <% if(person.name == 'Dave') { %>
    <li>This is definitely <%= person.name%>!!!</li>
    <% } else { %>
    <li>This is definitely not Dave!!! This is <%= person.name%></li>
    <% } %>
  <% } %>
</ul>
```

And that is pretty much how the template works.

### Additional not so basic **The Layouts**
Include npm install express-ejs-layouts first, then append `var expressLayouts = require('express-ejs-layouts');` line to the requirements at the top, then another line `app.use(expressLayouts);`. 

These lines will utilize a separate view file called layout.ejs which looks like a generic index.html file but at the body is ejs tag `<%- body %>` exists.

When you build a get router for a particular page with layout, this is how it looks:

```
app.get('/about', function(req, res){
  response.render('about');
})
```

It would still include whatever design you had in the layout file, then appends about data page at the end. The `get('/')` would also include the layout file at the top, then the dave list at the bottom.

### Final Addition **The Partials**
Right under the body ejs tag is where you'd want it to exist.

```
<body>
  <%- body %>
  <%- include('partials/onepartial') %>
</body>
```

Then would look for that file, and append it at the end after the body content of each page. It is mostly used for reusable text that you'd want to repeat at different parts.

Until I get to work on this, this is pretty much the tutorial.