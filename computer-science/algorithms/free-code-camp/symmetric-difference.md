# Symmetric Difference

## Problem

Create a function that takes two or more arrays and returns an array of the `symmetric difference` (`△` or `⊕`) of the provided arrays.

Given two sets (for example set `A = {1, 2, 3}` and set `B = {2, 3, 4}`), the mathematical term "symmetric difference" of two sets is the set of elements which are in either of the two sets, but not in both (`A △ B = C = {1, 4}`). For every additional symmetric difference you take (say on a set D = {2, 3}), you should get the set with elements which are in either of the two the sets but not both (`C △ D = {1, 4} △ {2, 3} = {1, 2, 3, 4}`).

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
* [Symmetric Difference](https://www.youtube.com/watch?v=PxffSUQRkG4)

## Solution

```javascript
function doIAdd(arr1, arr2) {
  var newArr = [];
  $.each(arr1, function(i, value) {
    if($.inArray(value, arr2) === -1) {
      newArr.push(value);
    }
  });
  $.each(arr2, function(i, value) {
    if($.inArray(value, arr1) === -1) {
      newArr.push(value);
    }
  });
  return newArr;
}
function sym(args) {
  var argsArray = [].slice.call(arguments);
  var currentArr = [];
  currentArr = doIAdd(argsArray[0], argsArray[1]);
  for (i = 2; i < argsArray.length; i++) {
    currentArr = doIAdd(currentArr, argsArray[i]);
  }
  var finalArr = [];
  $.each(currentArr, function(i, value) {
    if($.inArray(value, finalArr) === -1) {
      finalArr.push(value);
    }
  });
  args = finalArr.sort();
  return args;
}

sym([1, 2, 3], [5, 2, 1, 4]);
```

## Tests

* `sym([1, 2, 3], [5, 2, 1, 4])` should return `[3, 4, 5]`.
* `sym([1, 2, 3], [5, 2, 1, 4])` should contain only three elements.
* `sym([1, 2, 5], [2, 3, 5], [3, 4, 5])` should return `[1, 4, 5]`.
* `sym([1, 2, 5], [2, 3, 5], [3, 4, 5])` should contain only three elements.
* `sym([1, 1, 2, 5], [2, 2, 3, 5], [3, 4, 5, 5])` should return `[1, 4, 5]`.
* `sym([1, 1, 2, 5], [2, 2, 3, 5], [3, 4, 5, 5])` should contain only three elements.
* `sym([3, 3, 3, 2, 5], [2, 1, 5, 7], [3, 4, 6, 6], [1, 2, 3])` should return `[2, 3, 4, 6, 7]`.
* `sym([3, 3, 3, 2, 5], [2, 1, 5, 7], [3, 4, 6, 6], [1, 2, 3])` should contain only five elements.
* `sym([3, 3, 3, 2, 5], [2, 1, 5, 7], [3, 4, 6, 6], [1, 2, 3], [5, 3, 9, 8], [1])` should return `[1, 2, 4, 5, 6, 7, 8, 9]`.
* `sym([3, 3, 3, 2, 5], [2, 1, 5, 7], [3, 4, 6, 6], [1, 2, 3], [5, 3, 9, 8], [1])` should contain only eight elements.