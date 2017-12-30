# Missing letters

## Problem

Find the missing letter in the passed letter range and return it.

If all letters are present in the range, return undefined.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [String.prototype.charCodeAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
* [String.fromCharCode()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)

## Solution

```javascript
function fearNotLetter(str) {
  var strArray = str.split("");
  var numArray = [];
  for (var letter in strArray) {
    numArray.push(strArray[letter].charCodeAt(0));
  }
  for (i = 1; i < numArray.length; i++) {
    if (numArray[i] !== (numArray[i - 1] + 1)) {
      var missingNum = numArray[i - 1] + 1;
      var missingLetter = String.fromCharCode(missingNum);
      return missingLetter;
    }
  }
  str = undefined;
  return str;
}

fearNotLetter("abce");
```

## Tests

* `fearNotLetter("abce")` should return "d".
* `fearNotLetter("abcdefghjklmno")` should return "i".
* `fearNotLetter("bcd")` should return undefined.
* `fearNotLetter("yz")` should return undefined.