# Chunky Monkey

## Problem

Write a function that splits an array (first argument) into groups the length of `size` (second argument) and returns them as a two-dimensional array.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Array.prototype.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
* [Array.prototype.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

## Solution

```javascript
function chunkArrayInGroups(arr, size) {
  var newArr = [];
  for (i = 0; i < arr.length; i += size) {
  newArr.push(arr.slice(i, i + size));
  }
  return newArr;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```

## Tests

* `chunkArrayInGroups(["a", "b", "c", "d"], 2)` should return `[["a", "b"], ["c", "d"]]`.
* `chunkArrayInGroups([0, 1, 2, 3, 4, 5], 3)` should return `[[0, 1, 2], [3, 4, 5]]`.
* `chunkArrayInGroups([0, 1, 2, 3, 4, 5], 2)` should return `[[0, 1], [2, 3], [4, 5]]`.
* `chunkArrayInGroups([0, 1, 2, 3, 4, 5], 4)` should return `[[0, 1, 2, 3], [4, 5]]`.
* `chunkArrayInGroups([0, 1, 2, 3, 4, 5, 6], 3)` should return `[[0, 1, 2], [3, 4, 5], [6]]`.
* `chunkArrayInGroups([0, 1, 2, 3, 4, 5, 6, 7, 8], 4)` should return `[[0, 1, 2, 3], [4, 5, 6, 7], [8]]`.
* `chunkArrayInGroups([0, 1, 2, 3, 4, 5, 6, 7, 8], 2)` should return `[[0, 1], [2, 3], [4, 5], [6, 7], [8]]`.