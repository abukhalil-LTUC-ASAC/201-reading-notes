# Getting the bugs off the house

There is a reason why [entomophiles](https://en.wiktionary.org/wiki/entomophile) are not programmers, because we tend to like squishing bugs, over and over again until *nothing is left*.

Today we might learn about automatic scripting to deal with errors on its own. Understanding the flow is key, and misunderstanding the scope of variable ( local or global) is what causes most problems. Nested functions stack on each other, and the first function won't return anything until all above functions top-down have been resolved.

Each level in the stack (context) has two phases
1. Prepare: which gathers all `global > parent > local` variables, plus all function expressions on the same level and ready them up.
2. Execute: Fires all commands, with all declared functions on the same level and readjusts up or down the stack accordingly.

Errors are objects, and they contain `name`,`message`,`fileName`,`lineNumber`. Most frequent errors are built-in such as `SyntaxError`
and `ReferenceError`, plus the less common with their explanation:
* EvalError: Incorrect use of eval();
* URIError: which means some special characters did not [manage to escape](https://javascript.info/regexp-escaping) before their demise.
* TypeError: Whenever you use an incorrect or nonexisting method or object.
* RangeError: Since some functions have limited range input, such as `toFixed()` which only accepts between 1-20 to add digits after comma.

Debugging to force your desired outcome is the major practice, but sometimes with resources outside of your ability to manage, its impossible to predict the outcome, such as data request from a server you don't own, so instead you'd use `try`, `catch` and `throw` statement.

FYI, a good console logging involves multiple step by step initiation using console.info, warn and error plus special styling added.
Grouping is useful to make sure all relevant logs are collapsible.
```
console.group( ' Area calculations');
console.info('Width ', width);
console.info( 'Height ', height);
console.log(area);
console.groupEnd();
```
`console.Table(ObjectOrObjectArray)` makes use of neat display of such input.
`console.Assert(Condition, Output)` is a condition for console logging.
Breakpoints are a great way to check for values at that point by simply pressing on the number of the line. Reminds me of the simulation days. You could also move step at a time, step in and out of functions, and add conditional breakpoints to stop only if its true. Conditional or non conditional breakpoints could also be  manually entered into the code using keyword `debugger`.

Handling errors means **`try`**ing a piece of code, if it fails you'd want to log that with **`catch`** and let the script continue, with **`final`** adding an optional replacement such as page refresh and user message.

A preemptive **`throw`** helps adding your own useful information to errors you'd expect to happen, mostly because of data parsing of third party sources.
```
if (!isNaN(area)) {
  return area;
} else {
  throw new Error('calculateArea() received an invalid number')
}
```

## Practical TIPS
* Check for same errors in other browsers
* Check were the code stops by adding numbers
* Comment non-critical code blocks for the process to scale down the debugging
* Explain your work to someone else
* Stackoverflow
* Use code playgrounds before posting a problem
* Validate with online tools such as `jslint/jshint.com`
