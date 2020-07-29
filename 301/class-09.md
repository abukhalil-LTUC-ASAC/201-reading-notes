# To make readable functions for all.

Have you ever handled a code base of others? If you were blown away by its complexity, you could probably be sure that its also what others feel too when looking at your code base. Making elegance of code is not a random feat, and neither is the beauty and simplicity of human languages to their native users. 

What makes proper code, the code you can use and reuse, send over and receive a decade later and still be readable, is but a carefully highlighted bunch rules codeGrammarNazis made public for everyone who are willing to participate in the global exchange of code. It is quite important if you work individually or as a part of a cooperation, and is specially true if you want to contribute to open source projects.

So what makes programming code of a functional type, there are two main points, one relates to the base which is [immutability](https://en.wikipedia.org/wiki/Immutable_object), the other is about [pure functions](https://en.wikipedia.org/wiki/Pure_function). Which is quite interesting seeing that fresh coders would think the more complex your code looks, the better it might be perceived, but on the contrary, and just like spoken languages, talking *smart* in a trivial situation might make you sound arrogant or unpleasant the least. Context matters and when programming is as simple as it can and should be, its much better for the wider audience of future code maintainers.

## Pure Functions
To explain these concepts further, I'd invite you to read through [the Medium article](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa) on the matter, explaining pure functions first on multiple example:

* Firstly, it returns the same result if given the same arguments. (Using only inputs from parameters, Reading from files, Random Numbers)
* It does not cause any observable side effects. Such when you'd use a global variable as a parameter, then change that variable inside. (Counts as mutable in the immutability matter)

> Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.-TK @Medium

## Immutability
Basically use new variables instead of updating the old ones, for an example if you would want to add up a sum of an array, you'd instead use recursion as it does not change any variables, makes use of all possible sizes and returns the sum with no changes of state.
```

let list = [1, 2, 3, 4, 5];
let accumulator = 0;

function sum(list, accumulator) {
  if (list.length == 0) {
    return accumulator;
  }

  return sum(list.slice(1), accumulator + list[0]);
}

sum(list, accumulator); // 15
list; // [1, 2, 3, 4, 5]
accumulator; // 0

```
A major part from recursion is to use reduce(), which is coincides with today's topic and code challenge. 

## Pure Functions + Immutability
You might have noticed a funny part of having an unstoppable object facing an immovable wall. Thats when you have a two inherently different concepts when combined produces a [trivial solution](https://en.wikipedia.org/wiki/Irresistible_force_paradox). 
>Dr. Christopher Kaczor suggested that the need to change indicates a lack of power rather than the possession thereof.

So if both the function and variables that are great in their ability, but that it cannot use another variable, or have another value. Then you could replace them both with a constant, right? It is a great concept of caching complex reusable functions by simple calling its correspondent constant as a replacement called [memoization](https://en.wikipedia.org/wiki/Memoization).

## The first class

Using functions as values, and using it as data to do operations on it and return that value to the variable is what makes Functions as first-class entities, with the possibility of chaining data operations, higher and higher complex functions could be built, and eventually declared with a single line.

```

const sum = (a, b) => a + b;
const subtraction = (a, b) => a - b;

const doubleOperator = (f, a, b) => f(a, b) * 2;

doubleOperator(sum, 3, 1); // 8
doubleOperator(subtraction, 3, 1); // 4
```

## What is possible with the first class
Higher-order functions ofcourse! you might be familiar with most of them already, but should be functional in a way such as:
* **Filter**
```
const olderThan21 = person => person.age > 21;
const overAge = people => people.filter(olderThan21);
overAge(people); // [{ name: 'TK', age: 26 }, { name: 'Kazumi', age: 30 }]
```

* **Map**
```
let values = [1, 2, 3, -4, 5];
const updateListMap = (values) => values.map(Math.abs);
updateListMap(values); // [1, 2, 3, 4, 5]
```

* **Reduce**
Of which reduce will be explored as the most recent one. It does as what the name usually suggests with these Higher functions, as in reducing the resulting array such as it is smaller than the original, and doing the necessary operations on the mean time.
An example goes through filter, map and reduce to get a total of a specific item, instead of everything. This shows how far functional programming could turn everything to a much clearer code.

```

let shoppingCart = [
  { productTitle: "Functional Programming", type: "books", amount: 10 },
  { productTitle: "Kindle", type: "eletronics", amount: 30 },
  { productTitle: "Shoes", type: "fashion", amount: 20 },
  { productTitle: "Clean Code", type: "books", amount: 60 }
]

const byBooks = (order) => order.type == "books";
const getAmount = (order) => order.amount;
const sumAmount = (acc, amount) => acc + amount;

function getTotalAmount(shoppingCart) {
  return shoppingCart
    .filter(byBooks)
    .map(getAmount)
    .reduce(sumAmount, 0);
}

getTotalAmount(shoppingCart); // 70
```

### Check out [these exercises](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec).