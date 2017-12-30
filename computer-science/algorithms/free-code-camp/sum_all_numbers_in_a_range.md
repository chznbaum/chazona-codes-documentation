# Sum All Numbers in a Range

## Problem

We'll pass you an array of two numbers. Return the sum of those two numbers and all numbers between them.

The lowest number will not always come first.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
* [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
* [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

## Solution

```javascript
function sumAll(arr) {
  var arrMax = Math.max(arr[0], arr[1]);
  var arrMin = Math.min(arr[0], arr[1]);
  var sum = 0;
  for (i = arrMin; i <= arrMax; i++) {
    sum = sum + i;
  }
  return sum;
}

sumAll([1, 4]);
```

## Tests

* `sumAll([1, 4])` should return a number.
* `sumAll([1, 4])` should return 10.
* `sumAll([4, 1])` should return 10.
* `sumAll([5, 10])` should return 45.
* `sumAll([10, 5])` should return 45.