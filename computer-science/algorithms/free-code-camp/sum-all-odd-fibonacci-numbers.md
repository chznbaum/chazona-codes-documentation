# Sum All Odd Fibonacci Numbers

## Problem

Given a positive integer `num`, return the sum of all odd Fibonacci numbers that are less than or equal to `num`.

The first two numbers in the Fibonacci sequence are 1 and 1. Every additional number in the sequence is the sum of the two previous numbers. The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8.

For example, `sumFibs(10)` should return `10` because all odd Fibonacci numbers less than `10` are 1, 1, 3, and 5.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Remainder](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Remainder)

## Solution

```javascript
function sumFibs(num) {
  var fibNums = 1;
  var oldNum1 = 1;
  var oldNum2 = 1;
  var fibNumSum = 2;
  while (fibNums < num) {
    oldNum1 = oldNum2;
    oldNum2 = fibNums;
    fibNums = oldNum1 + oldNum2;
    fibNumSum += fibNums;
    if (fibNums % 2 !== 1) {
      oldNum1 = oldNum2;
      oldNum2 = fibNums;
      fibNums = oldNum1 + oldNum2;
      fibNumSum = fibNumSum - oldNum2 + fibNums;
    }
  } if (fibNums > num) {
    fibNumSum = fibNumSum - fibNums;
    num = fibNumSum;
  } else if (fibNums <= num) {
    num = fibNumSum;
  }
  return num;
}

sumFibs(4);
```

## Tests

* `sumFibs(1)` should return a number.
* `sumFibs(1000)` should return 1785.
* `sumFibs(4000000)` should return 4613732.
* `sumFibs(4)` should return 5.
* `sumFibs(75024)` should return 60696.
* `sumFibs(75025)` should return 135721.