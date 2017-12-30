# Mutations

## Problem

Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array.

For example, `["hello", "Hello"]`, should return true because all of the letters in the second string are present in the first, ignoring case.

The arguments `["hello", "hey"]` should return false because the string "hello" does not contain a "y".

Lastly, `["Alien", "line"]`, should return true because all of the letters in "line" are present in "Alien".

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [String.prototype.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)

## Solution

```javascript
function mutation(arr) {
  arr[0] = arr[0].toLowerCase();
  arr[1] = arr[1].toLowerCase();
  var newArr = arr[1].split("");
  for (i = 0; i < newArr.length; i++) {
    if (arr[0].indexOf(newArr[i]) === -1) {
      return false;
    }
  } return true;
    }
mutation(["hello", "hey"]);
```

## Tests

* `mutation(["hello", "hey"])` should return false.
* `mutation(["hello", "Hello"])` should return true.
* `mutation(["zyxwvutsrqponmlkjihgfedcba", "qrstu"])` should return true.
* `mutation(["Mary", "Army"])` should return true.
* `mutation(["Mary", "Aarmy"])` should return true.
* `mutation(["Alien", "line"])` should return true.
* `mutation(["floor", "for"])` should return true.
* `mutation(["hello", "neo"])` should return false.
* `mutation(["voodoo", "no"])` should return false.