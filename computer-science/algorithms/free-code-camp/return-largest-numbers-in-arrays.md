# Return Largest Numbers in Arrays

## Problem

Return an array consisting of the largest number from each provided sub-array. For simplicity, the provided array will contain exactly 4 sub-arrays.

Remember, you can iterate through an array with a simple for loop, and access each member with array syntax `arr[i]`.

Remember to use **Read/Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)

## Solution

```javascript
function largestOfFour(arr) {
  // Set up final array
  var newArr = [];
  // Sort each array largest to smallest and push to new array
  arr.forEach(function(i) {
    newArr.push(i.sort(function(a, b) {
      return b > a;
    })[0]);
  }); return newArr;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```