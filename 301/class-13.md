# Your basic guide to fill in that pesky form
Forms we have used in the [book app](https://abukhalil-book-app.herokuapp.com/) have been quite a convoluted web!
HTML 5 Forms follow [this standard](https://htmlreference.io/forms/), just in case you forgot.

```
<form action="/subscribe" method="post">
  <fieldset>
    <legend>Subscribe to the Newsletter</legend>
    <input type="email" name="email">
    <button>Ok</button>
  </fieldset>
</form>
```
There is an interesting case of rendering ejs tags into hidden inputs just to be able to post them over again.

We have been accustomed to post and get methods, and now forms gets to be explained through these methods.
The action attribute specifies the URl that we are targeting wether absolute or relative using either full `https://..`
or simply a `/url`.

With get, data is appended to the url as `data.query.keys` where `keys` are the ***names*** you had in the form
and its `value` is in the ***value*** parameter of that form

Post method has these in `data.body` instead. If you have no idea how to check it, do this:

-  Open the developer tools.
-  Select "Network"
-  Select "All"
-  Select "foo.com" in the "Name" tab
-  Select "Headers"

post has two advantages, password is hidden from the direct screen and has no limit to the amount of data you could send.

to handle these data in the server side of express do have a look into this [mozilla link](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs).

Check out further styling options with these [YouTube videos](https://www.youtube.com/playlist?list=PL4cUxeGkcC9g5_p_BVUGWykHfqx6bb7qK)