# The Tragedy that is Local Storage

In a brief summary of [The blog](http://diveinto.html5doctor.com/storage.html), local storage was the luxury coin of native app, making web app development almost impossible. Hacks came through in many forms, sizes and capabilities. Cookies were the beginning, with 4kb of storage it was not enough for anything useful, but would still annoy browsers by sending that amount with every HTTP request with no encryption at all.

## [Then Came the Browser Wars](http://en.wikipedia.org/wiki/Browser_wars#The_first_browser_war)

Sounds intriguing? Not exactly, unless you are into these stuff. However one of the outcomes were streams of update to storage capabilities, ***userData*** is something, done by microsoft in IE believing that it is *the solution*, but apparently it was just a solid, temporary answer to an ever demanding user experience development.

## Then Adobe trotted by.

Adobe, the flash player that everyone loves and hates, for it's uniqueness that the boomers could relate to, and it's security leaks that everyone else had heard of. I still in fact remember the part where it would ask for you to increase storage from 100kb to almost a premium 100mb's in the days of 100 GB hard drives.

## Gearing up for total domination

Google however provided a smart plan, by implementing SQLite based solution to the browser, it could store user data on servers, with unlimited data *forever*. This eventually led to the demise of adobe flash despite tons of efforts to unify the scattered solutions, and to raise a new HTML based solution that is [**HTML 5**](https://html.spec.whatwg.org/multipage/webstorage.html).

## Forward for victory

In addition to what gears offered, there was finally a local [key/value pair](https://searchenterprisedesktop.techtarget.com/definition/key-value-pair#:~:text=A%20key%2Dvalue%20pair%20(KVP,hash%20tables%20and%20configuration%20files.) solution that is persistent, non transmittable and is implemented natively across many platforms. Check it out using the following command.
```
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```

To start storage and access, you should know that all values are stored in strings so `parseInt(), parseFloat()` is a must for their perspective values. 
```
interface Storage {
  getter any getItem(in DOMString key);
  setter creator void setItem(in DOMString key, in any data);
};
``` 
getting a key with nonexisting value returns null, while setting existing ones updates them. And just like objects its possible to write as following brackets notation.
```
var foo = localStorage.getItem("bar");
// ...
localStorage.setItem("bar", foo);
```
could be rewritten to use square bracket syntax instead:
```

var foo = localStorage["bar"];
// ...
localStorage["bar"] = foo;
```
And ofcourse, `removeItem()` to remove the value of that key.

## Tracking enemy movement

totally familiar, using event listeners to window, which will be called if it fired, and something actually changed.
```
if (window.addEventListener) {
  window.addEventListener("storage", handle_storage, false);
} else {
  window.attachEvent("onstorage", handle_storage);
};
```

## Knowing yourself, and your weaknesses

"The answers, in order of importance, are “5 megabytes,” “QUOTA_EXCEEDED_ERR,” and “no.”". -http://diveinto.html5doctor.com/storage.html
Literally, 5 megabytes of storage, and error if it is exceeded, and no you can't ask for more.

## [Click me, and play](http://diveinto.html5doctor.com/examples/localstorage-halma.html)

Everything is a string, so act accordingly.

## Yet someone, is still gearing up

Remember gears from google? They are up to something sinister, and **huge**. What they actually do is wrap commands into SQL table commands and sends them off to the infinite storage.

And despite the huge competition against google and the other giants in pursuit of increasing SQL adaptation to their own standards, there is a small and notable player mentions which is [IndexedDB](http://dev.w3.org/2006/webapi/IndexedDB/). Make sure to follow up on [their tutorial](http://hacks.mozilla.org/2010/06/comparing-indexeddb-and-webdatabase/) though.

Things could be said about IndexDB, it did after all, get a reaction from the giants.

>At time of writing, IndexedDB has only been implemented in a beta version of Firefox 4. (By contrast, Mozilla has stated that they will never implement Web SQL Database.) Google has stated that they are considering IndexedDB support for Chromium and Google Chrome. And even Microsoft has said that IndexedDB “is a great solution for the web.”

[Keep an eye open for it.](http://diveinto.html5doctor.com/storage.html#further-reading)



