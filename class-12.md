# Setting up your drawing space

Not manually though, that would be hundreds of hours of repeated labour. We are using functions to automate repeated work after all, so might as well use functions made by others to do the same work we are doing!

Javascript libraries is going to be explored, which got to do specifically about charts. Just like what you'd use when doing a presentation and displaying data, Javascript library owners Chart.js made it possible to do the same using js data.

## Start with a `<canvas>`
Installation is simply done by either by download the [github](https://github.com/chartjs/Chart.js) js file and add `<script src='Chart.min.js'></script>`. Other way is to use the [CDN](https://www.cloudflare.com/learning/cdn/what-is-a-cdn/) and get the [specific link for Chart.js](https://cdnjs.com/libraries/Chart.js). Paste them as you would for a script source.

Whatever you add inside the tag will be treated as fallback element for unsupported browsers, otherwise it is ignored and canvas would render. Everything on the script lives on the rendered `<canvas>` tags, so make sure of that. Drawing a line chart as a simple example involves adding a footer element to get context.

```
<script>
    var buyers = document.getElementById('buyers').getContext('2d');
    new Chart(buyers).Line(buyerData);
</script>
```
and then you could use that with 

```
var buyerData = {
	labels : ["January","February","March","April","May","June"],
	datasets : [
		{
			fillColor : "rgba(172,194,132,0.4)",
			strokeColor : "#ACC26D",
			pointColor : "#fff",
			pointStrokeColor : "#9DB86D",
			data : [203,156,99,251,305,247]
		}
	]
}
```
and that is it, `datasets` and `Chart(context).typeChart(data)` is the repeated theme. For pie charts it would look like `.Pie(pieData, pieOptions);` instead, and uses pieData with values and colors only and pie options to define other properties.

Other topics to visit includes [drawing elements, styling and other possible uses such as animated works](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial). It is limited by the fact that canvas only supports rectangles and paths, but it could still draw many shapes out of it. eg.: Rectangle

```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.fillRect(25, 25, 100, 100); // color fill
    ctx.clearRect(45, 45, 60, 60); // clear fill with transparency
    ctx.strokeRect(50, 50, 50, 50);// rectangle outline fill
  }
}
```

and with a path and .moveTo helps drawing complex shapes with disconnects.

```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath(); // initialization
    ctx.moveTo(75, 50); // starting point
    ctx.lineTo(100, 75); // draw between start and line 1
    ctx.lineTo(100, 25); // draw in between line 1 and 2
    ctx.fill(); // solid fill inside of shape
  }
}
```
 ## advanced styling

 Other than fill and outline, there is fillStyle and outlineStyle which accepts math operations to do elegant and complex colorings.which results in:
```
  function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' + 
                         Math.floor(255 - 42.5 * j) + ')';
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }
  }
  ```
![stroke](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/253/c4e071f91f9aa7e0d29ff8696d37a27c/Canvas_strokestyle.png)

or even a proper pattern out of an image
```
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');

  // create new image object to use as pattern
  var img = new Image();
  img.src = 'https://mdn.mozillademos.org/files/222/Canvas_createpattern.png';
  img.onload = function() {

    // create pattern
    var ptrn = ctx.createPattern(img, 'repeat');
    ctx.fillStyle = ptrn;
    ctx.fillRect(0, 0, 150, 150);

  }
}
```
![pattern](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/222/bcf90d24adf679755d47e6e2adf31afa/Canvas_createpattern.png)

The tools requires extensive practice to get it right, one time uses is OK but it could go really heavy and make a website truly unique.