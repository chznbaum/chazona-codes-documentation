# Smallest Common Multiple

## Problem

Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

The range will be an array of two numbers that will not necessarily be in numerical order.

e.g. for 1 and 3 - find the smallest common multiple of both 1 and 3 that is evenly divisible by all numbers between 1 and 3.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Smallest Common Multiple](https://www.mathsisfun.com/least-common-multiple.html)

## Solution

```javascript
function commonMultiple(value1, value2, number) {
  while (number % value1 !== 0 || number % value2 !==0) {
    number += (value1);
  }
  return number;
}
function smallestCommons(arr) {
  arr = arr.sort();
  var newArr = [];
  for (i = arr[0]; i <= arr[1]; i++) {
    newArr.push(i);
  }
  var num = newArr[0];
  var val1 = newArr[0];
  var val2 = newArr[1];
  num = commonMultiple(val1, val2, num);
  for (i = 2; i < newArr.length; i++) {
    num = commonMultiple(num, newArr[i], num);
  }
  return num;
}


smallestCommons([1,5]);
```

## Tests

* `smallestCommons([1, 5])` should return a number.
* `smallestCommons([1, 5])` should return 60.
* `smallestCommons([5, 1])` should return 60.
* `smallestCommons([1, 13])` should return 360360.
* `smallestCommons([23, 18])` should return 6056820.