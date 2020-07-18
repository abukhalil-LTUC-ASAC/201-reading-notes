# Forging The One To Rule Them All

Not exactly the ring for the dark lord, but the web app for the dark square that is your phone. No one is his right mind would ever own a website that is incompatible to phone screen sizes, you are talking about as much as half of internet users if not more, lost to laziness.

Reading the [article](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/), it mentions the need for web apps to be responsive, adaptive or mobile. These three are similar, but the current trend wants to have the one solutions that is truly one in both as a solution and in maintenance. So responsiveness is what we will strive for. 

What you'd need to get started is ~~the Ring, an Elven Ringmaker/Lord, and Mount Doom~~ a comprehensive understanding of how flexible layouts, media queries, and flexible media are used.

## Flexible Layouts

or really, flexible grids are widely used since CSS3, allowing for [amazing results](https://www.youtube.com/watch?v=7kVeCqQCxlk) that was not as easy to get using pure CSS until now. Additionally, relative unit lengths `em` and  viewport `vw,vh` replaces pixel values in most cases.

## [Media Queries](https://css-tricks.com/css-media-queries/)

as in the exact device, or browser width selector. A way to define totally different set of rules for different devices.

media query asks the device for a couple information, and passes the styles if it matches with the query, starting with the declaration, then the device such as `all`, `tv` or even `braille`, followed by media features and values. 

`@media all and (min-width: 800px) and (max-width: 1024px) {...}` All media types between 800 and 1024 pixels wide.

`@media only screen and (orientation: portrait) {...}` Only screens in a portrait orientation.

`@media not screen and (color) {...}` Black and white or monochrome screens .

The features in a list are:
* Height & Width Media Features
The `height` and `width` values of the current viewport.

* Orientation Media Feature
if a device is in the `landscape` or `portrait`

* Aspect Ratio Media Features
`@media all and (min-device-aspect-ratio: 16/9) {...}` device specific values

* Resolution Media Feature
`resolution` as resolution of the output device in pixel density `dpi`, or dots per pixel `dppx`, dots per centimeter `dpcm`

* Other Media Features
  `color, color-index, monochrome`, `grid` for bitmaps and `scan` for tv.

## But first things first, Mobile First!

Which queries start as 
```
/* Default styles first then media queries */
@media screen and (min-width: 400px)  {...}
@media screen and (min-width: 600px)  {...}
@media screen and (min-width: 1000px) {...}
@media screen and (min-width: 1400px) {...}
```
You could notice it starts of as the smallest viewport, since they are the easiest and has the lowest content count, so why waste the effort and bandwidth of loading desktop content full web pages, only to delete and shift all of it to smaller content.

And do avoid using CSS3 shadows, gradients, transforms, and animations within mobile styles since they are bad for health, battery health that is.

## Viewport

The apple invention when they released the iPhone, why work on apps and web app code bases when you can just use one? 
`<meta name="viewport" content="width=device-width">` helps define the initial state of the viewport, and apply queries accordingly.

Other considerations:
* Viewport Scale that scales all values accordingly, `.. content="user-scalable=yes">` allows for zooming.
* Viewport Resolution has pixel by pixel control. `.. content="target-densitydpi=device-dpi">`
* Combining Viewport Values for best of both worlds solutions. `.. content="width=device-width, initial-scale=1`

## Flexible Media
***psst.. here is a quick cheat***:
```
img, video, canvas {
  max-width: 100%;
}
```
***and for embedded media:***
```
<figure>
  <iframe src="https://www.youtube.com/embed/4Fqg43ozz7A"></iframe>
</figure>

<style>
figure {
  height: 0;
  padding-bottom: 56.25%; /* 16:9 */
  position: relative;
  width: 100%;
}
iframe {
  height: 100%;
  left: 0;
  position: absolute;
  top: 0;
  width: 100%;
}
</style>
```

## How floats fit in?

Responsiveness isn't just about dimensions, its also about layout positioning that could go along different sizes. With media query defined you could specify that elements go otherwise from sideways to vertical alignment.

After floated elements, comes the clarity of `clear: both` that helps moving other elements under our floats as normal flow to avoid clutters.

You might have heard of the great collapse, but its a bane to UX and frontend designers as elements loose positioning due to parent having no height. Methods to solve it uses a couple of tricks involving clearing after floats but before the end of the parent container.

#### The Empty Div Method
`<div style="clear: both;"></div>` as simple as adding it after floats.
#### Overflow Method
By adding hidden or auto to the parent, it will try to contain it.
#### The Easy Clearing Method
Which is what I mostly use, by adding a pseudo class to the parents of floats.
```
.clearfix:after { 
   content: "."; 
   visibility: hidden; 
   display: block; 
   height: 0; 
   clear: both;
}
```

## Problems with Floats

I have dealt with tons of headache involving these, a quick rundown looks like: 
* Pushdown use `overflow: hidden` otherwise, floats get pushdown by *bigger than parent* media.
* Double Margin Bug `display: inline` to avoid [double margins](http://www.cssnewbie.com/double-margin-float-bug/).
* 3px Jog that affects text inside of floats, use width or height values.
* Bottom Margin Bug when children ignores parent both floated, in terms of children margin, use parent padding instead.

## Alternatives
Check these out.
[Text Wrappers](https://blog.ideashower.com/post/15139639050/css-text-wrapper#_=_)
[Faux Absolute Positioning](https://alistapart.com/article/fauxabsolutepositioning/) *I hate absolutes*
[CSS Templates](https://www.w3.org/TR/css-template-3/)

