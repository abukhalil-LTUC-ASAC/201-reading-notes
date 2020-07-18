# Adding users into the matrix

This is what is going to happen, we will add input html, and wait for users to use it! There are multiple ways to wait for their input.

## Your gateway

Most famous is google's search bar which is a text area input, and in between `<form></form>` tags, which has multiple properties such as:
* `action` is a url property that specifies where the data will go after submit
* `method` with either get or post is used to receive/send data and files to the url
* `id` helps to distinguish forms from elements and choosing which form correlates with which input type such as our text input form, others include: 
  * Adding Text
    1. Text Input: single line, you could specify `maxlength`<br>
    `<input name="Enter something." />`<br>
    <input name="Enter something." />
    2. Password Input: with a mask over input.<br>
    `<input type="password" name="Password" />`<br>
    <input type="password" name="Password" />
    3. Tex input: multiple lines <br>
    `<textarea>Enter Comments</textarea>`<br>
    <textarea>Enter Comments</textarea>

  * Making Choices
    1. Radio Buttons: as a unique choice
    <input type="radio" name="food" value="tuna" checked="checked"/>Tuna
    <input type="radio" name="food" value="chicken" />Chicken
    <input type="radio" name="food" value="beef" />Beef <br>
    ```
    <input type="radio" name="food" value="tuna" checked="checked"/>Tuna
    <input type="radio" name="food" value="chicken" />Chicken
    <input type="radio" name="food" value="beef" />Beef
    ```
    2. Checkboxes: as a multiple choice
    <input type="checkbox" name="food" value="tuna" checked="checked"/>Tuna
    <input type="checkbox" name="food" value="chicken" />Chicken
    <input type="checkbox" name="food" value="beef" />Beef <br>
    ```
    <input type="checkbox" name="food" value="tuna" checked="checked" />Tuna
    <input type="checkbox" name="food" value="chicken" />Chicken
    <input type="checkbox" name="food" value="beef" />Beef
    ```
    3. Dropdown: as a list of choices with also similarly a [`datalist`](https://www.w3schools.com/tags/tag_datalist.asp) tag to explore. You could add `multiple` attribute to allow multiple selections.
    <select name="food">
      <option value="tuna">iPod</option>
      <option value="chicken">Chicken</option>
      <option value="beef">Beef</option>
    </select><br>
    ```    
    <select name="food">
      <option value="tuna">iPod</option>
      <option value="chicken">Chicken</option>
      <option value="beef">Beef</option>
    </select>
    ```

  * Submitting Forms
    1. Submit Button: is a submit button with predefined css
    <input type="submit" name="subscribe" value="Subscribe" />
    `<input type="submit" name="subscribe" value="Subscribe" />`
    2. Image Button: uses `type="image"` and `src="image"` to replace the button with an image.
    3. File Upload: allows for file uploads and all the risks associated with it.
    <input type="file" name="user-song" /><br />
    `<input type="file" name="user-song" />`

Longer forms require good practices with html tag, such as the following form.
<fieldset>
<legend>Contact details</legend>
<label>Email:<br />
<input type="text" name="email" /></label><br />
<label>Mobile:<br />
<input type="text" name="mobile" /></label><br />
<label>Telephone:<br />
<input type="text" name="telephone" /></label>
</fieldset>

```
<fieldset>
<legend>Contact details</legend>
<label>Email:<br />
<input type="text" name="email" /></label><br />
<label>Mobile:<br />
<input type="text" name="mobile" /></label><br />
<label>Telephone:<br />
<input type="text" name="telephone" /></label>
</fieldset>

```
Other forms include date and search forms, along with HTML 5 new email and URL forms that also verifies if it is valid, allowing for browsers to run faster by offloading work from the processor with javascript.

## Cleaning up the matrix

There are multiple ideas on how to set a proper form for users to enter from, they mostly deal with three main objects which are reading the labels, using the input area and clicking submit. 

Best practices involve making a good layout, just like your HTMLCSS and that would fit inside your web without being abrupt. Others would even change `:hover` and `:focus` states of input area to include effects and also add background image. You could also define the cursor shape with `cursor` but only use it in a useful manner.

try using this template in your css for the fieldset and legend.

```
fieldset {
width: 350px;
border: 1px solid #dcdcdc;
border-radius: 10px;
padding: 20px;
text-align: right;}
legend {
background-color: #efefef;
border: 1px solid #dcdcdc;
border-radius: 10px;
padding: 10px 20px;
text-align: left;
text-transform: uppercase;
}
```

for unaligned elements, divs should surround each element in the form, then floated into their proper places with a specified width to avoid title misalignment.

## Starting up the party

With [tons of events](https://www.geeksforgeeks.org/javascript-events/) to handle, it is a huge party waiting to explode. [Our party](https://abukhalil95.github.io/cookie-stand/) for today involves adding locations to the project, dynamically through user input.

How does it work? At a basic level, HTML code has no events attached, but rather just has properties and acts as objects. With `event.listeners` and `el.onAction = function` you could attach any element on the DOM with these, and they will wait until your specified event fires! then executes!

Three properties are inputted into the event listener method.
`element.addEventListener('event',neededFunction,boolean)` To pass arguments inside the function use an anonymous function 
```
function(arguments){
  neededFunction(arguments);
};
```

Event flow understanding is important, since when you hover over a link, it also hovers over all of its parent elements, I had to use `stopPropagation()` to avoid clicks affecting parent click commands and executing [event bubbling](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation). Another famous case is `preventDefault()` for events that has other unintended behaviors just before our intended code.

Event object is important for any kind of interactions, and is defined with `target = event.target || event.srcElement` which then can be  used as any other object.

Things could get complicated, and eventually explode into a fiery display of overheated CPU and bloated RAM's if you overdid events assignment and manipulations. Don't be the chrome everyone hates.

The best part, is that there is a workaround to multiple event listeners of the same parent, just apply the listener to the parent instead. Then ask which target it is.

That target can be called using `this` keyword if no parameters are passed and the function is simply declared and has events attached. Or by passing the event parameter if an argument is declared using anonymous function.

Most used events are: 
* User interface events such as load, resize and scroll
* focus and blur for interactive elements such as links and forms
* Mouse events such as click, dblclick and mouseover
* Keyboard events such as input, keydown and keyup
* Form events with submit, change and input
* Mutation events for any DOM changes
* HTML 5 events which are interesting cases. DOMContentLoaded for when the basic DOM has been loaded but CSS, image and JS might not be.

[<button >Next</button>](https://abukhalil95.github.io/reading-notes/class-10)