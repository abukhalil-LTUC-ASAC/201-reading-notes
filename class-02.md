# [Additional](https://dictionary.cambridge.org/dictionary/english/additional) [HyperText](https://www.w3.org/WhatIs.html) [Markup](https://techterms.com/definition/html) [Language](https://www.webopedia.com/TERM/P/programming_language.html)

This second part will deal with particularities of TEXT, CSS styles and some sample JS instructions. 

## Text and Wordings

Your frequent tool sets are: 
1. Headings `<h1><h2>...<h6>` indicates importance and text size, and is being [used in SEO](https://www.reliablesoft.net/h1-tag).
2. Grouping paragraphs using `<p>` makes your life much easier than making a totally new class for it.
3. `<b><i></i><b>` for **Bold** and *Italic* ***Text***
4. For problems such as math notations `<sup><sub>` helps adding superscript and subscript numbers and texts.
5. On the code side, Whitespace that adds readability is highly desired among coders.
6. To add spaces in the front side, `<br /><hr />` is used instead.

All of these are called **structural markups**, they have a clear visual effect as they are intended to look.

**Semantic markups** however offer additional change in meaning of texts, and might have some visual effects along, with the following tags:

1. `<strong>` unlike bold, emphasizes the content's importance and not just a visual effect. They also don't mean differently to [the machine](https://www.seobility.net/en/wiki/Strong_and_Bold_Tags). Similarly with `<em>` and italics.
2. Quoting with `<blockquote cite="source">` is the way to go, and acronyms can be expanded on hover using `<abbr>`
3. Citations and Definitions using `<cite><dfn>` helps indicate their respective parts in the content with not much visual change.
4. Addresses wether email or physical uses `<address>` in a specific [hCard](https://en.wikipedia.org/wiki/HCard) format. Especially helpful to parsing tools.
5. Finally the changes to content could be shown through `<ins><del><s>` to show inserted, deleted and strikethrough content of which the latter shows unimportant but should not be deleted information.

## Stylish Text

Similarly to OOP in the previous note, CSS encases each style around a ***box*** of some sort, stacking them around and grouping them into even more detailed boxes in boxes. 
This is where the cascading effect shows, as in if you would start with the base element such as body and work through until you reach a paragraph, common styling rules get overwritten the deeper you go into detail, these details would still inherit previous not-overwritten values. Allowing for a general style as a whole, and quick special styling for each subsets of that whole.

```
body {
    font-family: Arial, Verdana, sans-serif;
    color: #ff3e80;
    }
article {
    color: #eeffff;
}
h1, h2 {
    color: #ee3e80;
    }
p {
    color: #665544;
    }
#id {
    color: #6655ff;
}
.class{
    color: #6655ff;
}
```
That syntax, selector into brackets and property then value is the way.

Best part is to somehow get all of the selectors ready to work with, since they will be heavily used in the frontend development. Especially Child `li>a`, Descendant `li a`, Adjacent Sibling `h1+p` and General Sibling `h1~p`.

## JS Moves

One mistake to avoid is not adhering to javascript sensibilities and mixing upper and lowercase when declaring functions and variables. 
Organize functions into code blocks, and try avoid too much nesting. Comments are a must before each new function to explain what it does, so you wont change it tomorrow when you forget about it.

The [old note](https://abukhalil95.github.io/learning-journal/first_steps) did well in explaining most of the syntax, and don't forget to [loop](https://abukhalil95.github.io/learning-journal/foreverAgrind)

<button name="button" onclick="https://abukhalil95.github.io/reading-notes/class-03">Next</button>
