# Arguments Optional

## Problem

Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

For example, `addTogether(2, 3)` should return `5`, and `addTogether(2)` should return a function.

Calling this returned function with a single argument will then return the sum:

`var sumTwoAnd = addTogether(2);`

`sumTwoAnd(3)` returns `5`.

If either argument isn't a valid number, return undefined.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* [Arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)

## Solution

```
function addTogether() {
  function isNumber(num) {
    if (typeof num !== "number") {
      return undefined;
    } else if (typeof num === "number") {
      return num;
    }
  }
  for (i = 0; i < arguments.length; i++) {
    var numberCheck = isNumber(arguments[i]);
    if (!numberCheck) {
      return undefined;
    }
  }
  if (arguments.length > 1) {
    var a = isNumber(arguments[0]);
    var b = isNumber(arguments[1]);
    if (a === undefined || b === undefined) {
      return undefined;
    } else {
      var sum = a + b;
      return sum;
    }
  } else {
    var c = arguments[0];
    if (isNumber(c)) {
      return function(secondArgument) {
        if (c === undefined || isNumber(secondArgument) === undefined) {
          return undefined;
        } else {
          return c + secondArgument;
        }
      };
    }
  }
  return false;
}

addTogether(2,3);
```

## Tests

* `addTogether(2, 3)` should return 5.
* `addTogether(2)(3)` should return 5.
* `addTogether("http://bit.ly/IqT6zt")` should return undefined.
* `addTogether(2, "3")` should return undefined.
* `addTogether(2)([3])` should return undefined.