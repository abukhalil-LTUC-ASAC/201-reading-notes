# [Node.JS](https://www.sitepoint.com/an-introduction-to-node-js/)

The backbone of JS backend, it is time to get introduced to the [everything in the internet world](https://medium.com/commencis/javascript-is-everywhere-really-906d1cf06092). You probably heard of it as a hot backend for tech companies who are after the most recent technologies. Others simply call it the [Javascript Runtime](https://www.infoworld.com/article/3210589/what-is-nodejs-javascript-runtime-explained.html). 

There is another aspect of JS, that it has an [open standard](https://stackoverflow.com/questions/5520245/is-javascript-an-open-source-project), might try something with IOT using it.

Best part is that it gets excellent support, being part of the v8 engine development that is also the latest, duh.
It also is what we know as `npm`.

The rest is where you'd want to develop your skills on, wether to build front or backend, mobile or desktop or even IOT using its own engine in JS. It is truly everywhere.

## Some about Servers

So you have your computer (Client), and there is another computer (Server) that owns content. You request that content through a mail service (HTTP - HyperTextTransferProtocol) that will get it from your address (IP - InternetProtocol), and send it to him (Server IP). The get and send is also called `Get`,`Post` requests. Other requests include `Put`, `Patch` and `Delete` which mostly follow the current [RESTful architecture](https://apievangelist.com/2012/12/20/history-of-apis).

So how node.js handles this data? Normally just like any other languages, not. With past traditional methods, a single call used to have its own thread and [`I/O`](https://en.wikipedia.org/wiki/Input/output) operations, then would wait until that is finished before changing or requesting anything other. Node JS differs by having a single thread but with async (asynchronous) functionality, and a callback attached if it wants to start up a new `I/O` operations so that when the first one finishes the later could be continued.

The issue with callbacks is with callback hell that is this [website](http://callbackhell.com/), its when you would try to understand nested callbacks bottom top, and fail to do so due to complexity. Another issue is when you'd get tons of errors in that single thread, better manage it quickly and offload any calculation intensive `I/O` to the [worker thread](https://blog.logrocket.com/node-js-multithreading-what-are-worker-threads-and-why-do-they-matter-48ab102f8b10/).

Async functionality lends its immense usefulness with real time data interactions, such as social platforms. Using micro-services and tons of API's with `I/O` operations are another aspect. But even then, due to simplicity of Node.js, there is absolutely no reason not to use it. It is after all, truly everywhere.
