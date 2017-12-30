# Boo who

## Problem

Check if a value is classified as a boolean primitive. Return true or false.

Boolean primitives are true and false.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Boolean Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

## Solution

```javascript
function booWho(bool) {
  // What is the new fad diet for ghost developers? The Boolean.
  if (bool === true || bool === false) {
    bool = true;
  } else
    bool = false;
  return bool;
}

booWho(null);
```

## Tests

* `booWho(true)` should return true.
* `booWho(false)` should return true.
* `booWho([1, 2, 3])` should return false.
* `booWho([].slice)` should return false.
* `booWho({ "a": 1 })` should return false.
* `booWho(1)` should return false.
* `booWho(NaN)` should return false.
* `booWho("a")` should return false.
* `booWho("true")` should return false.
* `booWho("false")` should return false.