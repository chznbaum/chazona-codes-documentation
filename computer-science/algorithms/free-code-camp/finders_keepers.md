# Finders Keepers

## Problem

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument).

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Solution

```javascript
function findElement(arr, func) {
  var num = 0;
  var numArray = [];
  numArray = arr.filter(func);
  num = numArray[0];
  return num;
}

findElement([1, 2, 3, 4], function(num){ return num % 2 === 0; });
```

## Tests

* `findElement([1, 3, 5, 8, 9, 10], function(num) { return num % 2 === 0; })` should return 8.
* `findElement([1, 3, 5, 9], function(num) { return num % 2 === 0; })` should return undefined.