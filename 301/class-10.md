# Organizing the mess that is your code in JS

What would computers do, is what you'd normally do it when clearing out a to-do list, but rather than dealing with the oldest in the list first, the engine lists all possible functions calls until the deepest level into a single column, starting with the newest, and work its way out till all functions were made account for. The method is called LIFO.

> LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns. -[Charles Freeborn @freecodecamp](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/)

That part, of which data is *stacked* unto each other, is what makes JS with predictable functions calls, a synchronous engine to do code in.
Stack overflow, not the helpful website of which you'd copy paste answers from, happens when recursions with no exit or end happens during code execution. 

## So what about error checking?

A list of what you'd normally counter is useful in a sense of knowing where to look.

* Reference errors, happens when you don't declare variables before using it.
* Syntax errors, when weirdly positioned `{}`, `,`,`''` and many others are thrown around the code. Including syntax as in reserved words and functions typos.
* Range errors while giving negative or impossible ranges to objects such as arrays. 
* Type errors after trying to access undefined properties in an object.

[And even more list of errors](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors).

## Debugging

A plus technique would be to get used to using breakpoints, with additional conditional statements to fine tune what you would expect from a function rather than looking at the whole output with console logs.

## Using the call stack

In addition to breakpoints, a `debugger` statement is useful that it shows what happened before that statement, in the call stack. Pressing continue allows for additional statements of debugger to run and how what happened next. Using semantic function names and validating input parameters makes looking at the call stack much easier. It can also be logged with the same results with `console.trace();`

## Dealing with the bugs

A spray would effective, if it was of byte origins. However many problematic functions could be enveloped with `try...catch` statement where if its an error or not, the output would show it and would continue normally regardless. The console would show the operation first rather than `unhandled error`. It is also important to note that with errors it would continue normally, other dependant functions later should take in mind the bad output.

> I would recommend using try…catch when the type checks are becoming “longer than your function logic”, when a request is made and you aren’t sure if the response might change or temporarily when a code is continuously giving you problems and you still haven’t got around to refactor it. -[Diogo Spínola @codeburst.io](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c);

Tools such as [qoukka](https://quokkajs.com/) and [eslint](http://eslint.org/) is what I might use to make life easier.
