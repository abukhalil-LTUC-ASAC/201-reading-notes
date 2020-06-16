# Getting the curves right

Which is all about css positioning and box models, as long as you have the stamina to power through this. It is going to be alright.

Continuing off from our [*previous lesson*](https://abukhalil95.github.io/reading-notes/class-08), we will deal with:
* multiple screen sizing across all devices, which all will have access to our website.
* multiple page sizing due to the consequence of having multiple screen sizings.
* varying ways a viewer would interact with your web page.

Often times there are web pages that uses fixed width layout, using all measurements in pixels. These offer easier control but have [disastrous](https://vanseodesign.com/css/css-layout-patterns-part-1/) effect of using devices other than a desktop with a widely used resolution screen.

Liquid layouts stretch along and covers your whole browser, I use them with percentage values all over. They look hacking-ly responsive but it's extremely hard to control your desired outcome.

Layout Grids is an awesome concept to organize your content around. Basically cut up your website into columns - depending on how much content you want to fit in a row - then arrange them starting with a column and ending by another if needed.

Using a framework to decide on a layout grid is a fine starting point without sacrificing customizability and cleanliness of code. One of them are [960 Grid System](http://www.960.gs)

Getting custom styles in different stylesheets is a good way to keep in control what they do, since they usually control a particular effect rather than the whole page. Use `@import url("this.css");` in the css file or `<link rel="stylesheet" type="text/css href="css/this.css>` in the HTML file.

[<button >Next</button>](https://abukhalil95.github.io/reading-notes/class-09)