# [The](https://en.wikipedia.org/wiki/The) [HyperText](https://www.w3.org/WhatIs.html) [Markup](https://techterms.com/definition/html) [Language](https://www.webopedia.com/TERM/P/programming_language.html)

Adding up to the [***previous one page knowledge***](https://abukhalil95.github.io/learning-journal/the_3w) is a comprehensive longer one page look into the topic.

As you have noticed, it does not take much to understand the code, and especially plain HTML and CSS code. Although this understanding will amplify your contribution as a non-tech person in any web related work by multiple folds wether as a designer, marketer or even general manager.

So what really happens when you click a link in your browser? Or what is even a [browser](https://www.mozilla.org/en-US/firefox/browsers/what-is-a-browser/)? I do recommend a detailed [video by Khan Academy](https://youtu.be/1K64fWX5z4U) that beautifully explains the whole process. [Basically this is how I would explain it]((https://wsvincent.com/what-happens-when-url/)):

1. You enter a URL into a web browser
2. The browser looks up the [IP address](https://computer.howstuffworks.com/internet/basics/what-is-an-ip-address.htm) for the domain name via [DNS](https://www.cloudflare.com/learning/dns/what-is-dns/)
3. The browser sends a [HTTP](https://www.webopedia.com/TERM/H/HTTP.html) request to the server
4. The server sends back a HTTP response
5. The browser begins rendering the HTML
6. The browser sends requests for additional objects embedded in HTML (images, css, JavaScript) and repeats steps 3-5.
7. Once the page is loaded, the browser sends further [async](https://stackify.com/when-to-use-asynchronous-programming) requests as needed.

And that is the whole process. I think<sub>*scratches head*</sub>. 

## Structures, or how your project won't become a mess.

HTML document is defined as following.
```
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <div>
            <h1>My First Heading</h1>
        </div>
        <div>
            <p>My first paragraph.</p>
        </div>
    </body>
</html>
```
With `<html><head><title><body>` being mandatory tags that needs to exist. with `<!DOCTYPE html>` helping editors and browsers to pre-define the document at hand. 

Tags `<div>` sometimes require ending tags `</div>`, others called void tags or self closing tags such as `<br>` and those who have optional ending tags but its recommended to close them anyway.

There is a convention used by the new HTML 5, which transformed how your common tags such as `<div><div><div>` are used in a more explicit way and become more meaningful `<article><aside><footer>` which are called [Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp). The details on what is what when speaking about element vs tag could be explored [**here**](https://www.456bereastreet.com/archive/200508/html_tags_vs_elements_vs_attributes/)

Advanced practices include adding comments:
```
<!-- To express a idea or why this part of the code is here and what it does -->
```
Adding ID and class attributes in a sound manner to differentiate elements when applying css and *moves*<sup>javascript</sup>, grouping parts of code or content together using `<div>` or `<span>` and finally using `<iframes>` to display content from other pages and `<meta>` tags to help search engines define your webpage.

## Jumping to the action

Scripting your way to success usually means trial and error, rinse and repeat. The same could be said about scripts in a computer, iterating through your failures until something good happens, methodically. 

Understanding what you want to do, and get some kind of [process and flowchart such as this kookie maker](https://gojs.net/latest/samples/flowchart.html) made, then translate it to machine language so that it could understand what you want done is your first step. 

Tasks are broken down, each time you find it too complicated, break it down again until its as simple as adding variables, implementing them into a function and loading up a result.

More on how the computer really looks at our problems is through this excellent piece by the [FCC.org](https://www.freecodecamp.org/news/object-oriented-programming-concepts-21bb035f7260/) Titled: How to explain object-oriented programming concepts to a 6-year-old.

## Making a mashed HTML,CSS and JS webpage mmmm

From the past posts in the [learning journal](https://abukhalil95.github.io/learning-journal/), its apparently clear how to link different files together. A `<link rel= "stylesheet" href="styles.css"/>` for our CSS, and a `<script src="js/add-content.js">` for our JS files. The only real part left is to add some content and make something happen.

> Think like a computer and I guarantee you you'd find a way to do it, at a small cost of your ~~sanity~~ brain power. -Yahya Abu Khalil

