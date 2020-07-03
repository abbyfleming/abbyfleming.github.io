### Defined

Higher Order Functions
: A function that takes in a function (as a parameter) or returns a function. This helps your code be more "DRY" and makes testing easier by keeping functions smaller. `.filter()`, `.map()`, and `.reduce()` are all higher order functions!

### Examples

This function allows you to pass in a second parameter (another function!) that modifies the array.

```js
const modifyArray = (array, instructions) =>
	array.reduce((result, e) => {
			result.push(instructions(e));
			return result;
	}, [])

const clapback = (input) => {
	return `${input} 👏`
}

const chopLastLetter = (input) => {
	const chopped = input.substring(0, input.length - 1);
	return `${chopped} 🔪`;
}

const clap = modifyArray(["higher", "order", "function"], clapback);
// ["higher 👏", "order 👏", "function 👏"]

const chop = modifyArray(["higher", "order", "function"], chopLastLetter);
//  ["highe 🔪", "orde 🔪", "functio 🔪"]
}
```

Functions can be passed into other functions:

```js
const playMathGame = (x, y, operation) => {
	return operation(x, y);
}

const add = (x, y) => x + y;

const subtract = (x, y) => x - y;

const multiply = (x, y) => x * y;

const divide = (x, y) => x / y;

playMathGame(2, 5, add); // 7
playMathGame(10, 5, subtract); // 5
playMathGame(2, 2, multiply); // 4
playMathGame(10, 5, divide); // 2
```


### Learn more

* https://medium.com/humans-create-software/a-dirt-simple-introduction-to-higher-order-functions-in-javascript-b33bf9e19056


