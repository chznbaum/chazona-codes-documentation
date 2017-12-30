# Steamroller

## Problem

Flatten a nested array. You must account for varying levels of nesting.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Array.isArray()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)

## Solution

```javascript
function steamrollArray(arr, newArr) {
  // I'm a steamroller, baby
  if (!newArr) {
    newArr = [];
  }
  for (var item in arr) {
    if (Array.isArray(arr[item])) {
      steamrollArray(arr[item], newArr);
    } else if (!Array.isArray(arr[item])) {
      newArr.push(arr[item]);
    }
  }
  arr = newArr;
  return arr;
}

steamrollArray([1, [2], [3, [[4]]]]);
```

## Tests

* `steamrollArray([[["a"]], [["b"]]])` should return `["a", "b"]`.
* `steamrollArray([1, [2], [3, [[4]]]])` should return `[1, 2, 3, 4]`.
* `steamrollArray([1, [], [3, [[4]]]])` should return `[1, 3, 4]`.
* `steamrollArray([1, {}, [3, [[4]]]])` should return `[1, {}, 3, 4]`.