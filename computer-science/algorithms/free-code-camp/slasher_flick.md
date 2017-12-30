# Slasher Flick

## Problem

Return the remaining elements of an array after chopping off `n` elements from the head.

The head means the beginning of the array, or the zeroth index.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Array.prototype.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
* [Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

## Solution

```javascript
function slasher(arr, howMany) {
  // it doesn't always pay to be first
  arr.splice(0, howMany);
  return arr;
}

slasher([1, 2, 3], 2);
```

## Tests

* `slasher([1, 2, 3], 2)` should return `[3]`.
* `slasher([1, 2, 3], 0)` should return `[1, 2, 3]`.
* `slasher([1, 2, 3], 9)` should return `[]`.
* `slasher([1, 2, 3], 4)` should return `[]`.
* `slasher(["burgers", "fries", "shake"], 1)` should return `["fries", "shake"]`.
* `slasher([1, 2, "chicken", 3, "potatoes", "cheese", 4], 5)` should return `["cheese", 4]`.