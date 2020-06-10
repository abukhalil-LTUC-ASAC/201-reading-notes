# Being a content creator

This is your bulk of content, expressed in elements with images, text and color. And as with any part of web development, they require as much attention to detail. 

## Images, snapshots, facades, mirrors and visions

Wether you use it for it's face value, express an idea, or even change the general vibe of your web app these are the guidelines to follow. 
* Choice is important, as images do speak a thousand words. Sometimes in an unintentional way.
* Storage in an organized manner, neat standards that follows the rest of the project.
* Attributes to define: source, alt, width, height and the actual inline element `<img>` in the intended area of the code.

The rules however dictates proper usage of the tag, such as formatting in `png` for low color count, `jpeg` for high resolution imagery or `gif` for moving images, correct size to avoid overstretching and longer load times for small and big images, along with the right resolution capped at 72ppi.

The magic of stretchable images comes in the form of vector imagery, with its advanced form of [scalable vector graphics (SVG)](https://www.adobe.com/devnet/svg.html). It simply expresses images as numbered dots in a grid and connects them with lines then fills them with color, and stretching it in any direction will still keep the relative position of dots intact.

HTML 5 element `<figure>` and `<figcaption>` inside helps define images with their respective captions in a predesignated style.

## Colors, or how things look

Moving forward from the [previous introduction](https://abukhalil95.github.io/learning-journal/zen_1), it is apparent that many details are still left unsaid. So lets define all the details, properly:
* [**Contrast**](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference#contrast) [Light/Dark] defines the relative ease to read a text, depending on its own color and the background.
* **HSL** and **HSLA** came along with [CSS3](https://developer.mozilla.org/en-US/docs/Archive/CSS3) as an alternative way to define colors.
    1. **Hue** [0-360] defines the colors as if you would arrange them around a wheel.
    2. Low **Saturation** [0-100] is like when you'd use a sandpaper on a colored wall.
    3. **Lightness** [0-100] fills the color with either white or black, with the middle to be default normal.
    4. **Alpha** [0-1] or opacity is a useful tool to display an element's background or parent element.

## Nothing can justify a bad [design](terrible_text_layout)
So take note of the following, starting with two types of properties, those that changes how it literally looks such as [fonts](https://fonts.adobe.com/fonts), and how it relatively looks to its surroundings such as its color and spacing between lines and such. Here are the most used property list:
* [**Typefaces**](http://www.typogui.de/) with `font-family` are a bunch of font families that are grouped depending on style.
* **Wight** as in light, bold, black and other emphasis properties.
* **Style** such normal, italic and oblique.
* **Stretch** as in literally bunch or stretch words with condensed, regular and extended.

Typefaces are usually limited to 3 families, [along with another 3 for older browsers](https://blog.prototypr.io/typography-and-cross-browser-compatibility-fc1fa3b8fa9a), and additionally each browser has limited support for fonts so it's ideal to [generate other variations](https://www.fontsquirrel.com/tools/webfont-generator).

Other useful decorations to use are:
* line-height, letter and word spacing to change in-between line, word and letter spacing.
* alignment to move text accordingly.
* text-shadow for better visuals of overlapping texts above images or deep colors. Its fairly complicated and looks as such:
```
p.one {
background-color: #eeeeee;
color: #666666;
text-shadow: 1px 1px 0px #000000;}
```
Useful selectors indicate parts of text to manipulate such as:
* :first-letter, :first-line of text to change.
* :links, :visited for link manipulation.
* :hover, :active and :focus that highlights elements with mouse hover, or is active by being pressed on, or if it is [in focus](https://www.w3schools.com/cssref/tryit.asp?filename=trycss_sel_focus).

Finally, other attribute selectors are best to [*be practiced upon*](https://flukeout.github.io/), as they will be used sparingly but has great use in highly interactive apps.

<button name="button" onclick="https://abukhalil95.github.io/reading-notes/class-06">Next</button>




