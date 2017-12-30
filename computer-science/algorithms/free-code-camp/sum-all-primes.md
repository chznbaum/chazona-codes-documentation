# Sum All Primes

## Problem

Sum all the prime numbers up to and including the provided number.

A prime number is defined as a number greater than one and having only two divisors, one and itself. For example, 2 is a prime number because it's only divisible by one and two.

The provided number may not be a prime.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [For Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [Array.prototype.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

## Solution

```javascript
function sumPrimes(num) {
  var primeArray = [];
  var nonPrimeArray = [];
    for (i = 2; i <= num; ++i) {
      if (!nonPrimeArray[i]) {
        primeArray.push(i);
        for (var j = i; j <= num; j += i) {
          nonPrimeArray[j] = true;
        }
      }
    }
    var primesSum = primeArray.reduce(function(total, currentPrime) {
    return total + currentPrime;
  });
  return primesSum;
}

sumPrimes(10);
```

## Tests

* `sumPrimes(10)` should return a number.
* `sumPrimes(10)` should return 17.
* `sumPrimes(977)` should return 73156.