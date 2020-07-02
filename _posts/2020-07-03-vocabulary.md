Higher Order Functions
: A function that takes in a function (as a parameter) or returns a function. This helps DRY up your code and makes testing easier by keeping functions smaller.

Example: This function allows you to pass in a second parameter (another function!) that modifies the array.

```js
const buildSentence = (array, instructions) =>
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

const clap = buildSentence(["high", "order", "function"], clapback);
// ["high 👏", "order 👏", "function 👏"]

const chop = buildSentence(["high", "order", "function"], chopLastLetter);
//  ["hig 🔪", "orde 🔪", "functio 🔪"]
}
```

