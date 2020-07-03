# Animating everything on CSS

[Check out this link though!](https://engineerbabu.com/blog/css-transitions-and-animations/)
## Transform
Translate gives the ability to change the size, position and elements as a whole, both in 2d and 3d settings. Keywords as stated below is what will be frequently used.

<details>
<pre>
  <summary>- Scale</summary>

values larger or smaller than 1 scales the element accordingly, around the center point. Syntax follows: 

```
.box-1 {
  transform: scaleX(.5);
}
.box-2 {
  transform: scaleY(1.15);
}
.box-3 {
  transform: scale(.5, 1.15);
}
```
</pre>
</details>

<details>
<pre>

  <summary>- Rotate</summary>

This property allows for element rotation around it's center point by default, with positive for clockwise rotation and negative for counter clockwise.

```
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```
</pre>
</details>

<details>
<pre>

  <summary>- Skew</summary>

A distortion effect used to pull elements around their horizontal, vertical or a bit of both, as if you pushed the sides until the corner reaches the angle with its center. It uses `deg` values.

```
.box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```
</pre>
</details>

<details>
<pre>

  <summary>- Translate</summary>

Which moves the element as a whole from its center, without affecting any other element around it, similar to positioning with fixed. Using pixels and percentages with `(x,y)` to change them according to the perspective axis. Percentage means relative to its total x or y length.

```
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```
</pre>
</details>

<details>
<pre>

  <summary>- Combination</summary>

It is important to note only one transform per element can be declared, as it will overwrite the previous with next transform property. Instead they will be bunched with spaced in between.

```
.box-1 {
  transform: rotate(25deg) scale(.75);
}
.box-2 {
  transform: skew(10deg, 20deg) translateX(20px);
}
```

</pre>
</details>

<details>
<pre>

  <summary>Transform Origin</summary>

Changing the center of transformation allows for really interesting effects. As it allows for transitions around the edges or sides and different scaling looks. The value specifies the vertical and horizontal axes or each separately.

```
.box-1 {
  transform: rotate(15deg);
  transform-origin: 0 0;
}
.box-2 {
  transform: scale(.5);
  transform-origin: 100% 100%;
}
.box-3 {
  transform: skewX(20deg);
  transform-origin: top left;
}
.box-4 {
  transform: scale(.75) translate(-10px, -10px);
  transform-origin: 20px 50px;
}
```

</pre>
</details>

<details>
<pre>

  <summary>Browser Support Syntax (Vendor prefixes)</summary>
The general syntax is done by using `transform: value` plus any prefix for browser support.

```
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

</pre>
</details>

3D transformations are of a topic that can be revised in [this website](https://learn.shayhowe.com/advanced-html-css/css-transforms/#perspective) but apparently it is not widely used, since most web applications require simplicity and clarity, especially when considering mobile usage and small screens. However, look for niche works with 3D webs such as simulation works and the gaming industry in general!

## Transition

Transitions lend themselves a good portion of animation, through displaying changes in an element between two or more states in a smooth way. The other state is usually defined in the CSS pseudo classes `:hover`, `:focus`, `:active` and `:target`.

<details>
<pre>

  <summary>- Transition-property</summary>

Properties with no half-point cannot be transitioned for the obvious reason as it cannot be transitions. Such as `display` which has two absolute values. Multiples are declared in the same line `transition-property` and separated by comma.

The list of transition friendly properties are

background-color  || background-position ||   border-color ||
border-width      ||  border-spacing     ||     bottom  ||
clip              ||      color          ||     crop  ||
font-size         ||    font-weight      ||     height  ||
left              ||   letter-spacing    ||   line-height ||
margin            ||    max-height       ||    max-width  ||
min-height        ||     min-width       ||     opacity ||
outline-color     ||  outline-offset  ||  outline-width ||  padding ||
right || text-indent || text-shadow || top  || vertical-align ||
visibility || width || word-spacing || z-index

</pre>
</details>

<details>
<pre>

  <summary>- Transition-duration</summary>

Defines the time needed to get the transition for each property, multiple properties are defined with durations separated by comma with each index refers to the property in the same index. 

```
.box {
  background: #2db34a;
  border-radius: 6px;
  transition-property: background, border-radius;
  transition-duration: .2s, 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
  border-radius: 50%;
}
```

</pre>
</details>

<details>
<pre>

  <summary>- Transition-timing-function</summary>

With the time defined, speed could also be specified along the transition, it has multiple keywords that can be used together such as `linear`, `ease-in`, `ease-out`, `ease-in-out`. 

To explore the function and how it works, [check out this website](http://www.roblaplaca.com/examples/bezierBuilder/), which can be set using `cubic-bezier(x1, y1, x2, y2)`. Additional values include `step-start`, `step-stop`, and a uniquely identified `steps(number_of_steps, direction)` value.

```
.box {
  background: #2db34a;
  border-radius: 6px;
  transition-property: background, border-radius;
  transition-duration: .2s, 1s;
  transition-timing-function: linear, ease-in;
}
.box:hover {
  background: #ff7b29;
  border-radius: 50%;
}
```

</pre>
</details>

<details>
<pre>

  <summary>- Transition-delay</summary>

ِAlong with everything stated, this value sets a delay timer in seconds to the transition. As simple as that.

</pre>
</details>

<details>
<pre>

  <summary>Shorthand Form</summary>

Code could look very messy and have long lines that could be substituted with single liners that is readable and elegant. The rule is to have an order with `transition-property`, `transition-duration`,` transition-timing-function`, `lastly transition-delay` and separated by commas for different transitions.

```
.box {
  background: #2db34a;
  border-radius: 6px;
  transition: background .2s linear, border-radius 1s ease-in 1s;
}
.box:hover {
  color: #ff7b29;
  border-radius: 50%;
}
```

</pre>
</details>

## Keyframes

Keyframes adds just the right amount of control needed to make it the way you intended for the animation to roll. It splits the animation apart into different stages instead of having 2 states only. The split can be defined by position using `From-to approach` in pixels and `Percentage approach` for relative percentage value.

<details>
<pre>

  <summary>How it is used?</summary>

The top priority is to add `animation-name` as the way transition will happen such as `step` or `slide`, and the duration needs to be specified. Additionally:

```
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
.stage {
  height: 150px;
  position: relative;
}
.ball {
    height: 50px;
    position: absolute;
    width: 50px;
}
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
}
```

</pre>
</details>

There are additional [custom animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/#customizing-animations) that could be handy to really make your web app *move*. 

[<button >Next</button>](https://abukhalil95.github.io/reading-notes/class-14b)