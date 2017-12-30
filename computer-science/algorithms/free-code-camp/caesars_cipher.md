# Caesars Cipher

## Directions

One of the simplest and most widely known `ciphers` is a `Caesar cipher`, also known as a `shift cipher`. In a `shift cipher` the meanings of the letters are shifted by some set amount.

A common modern use is the [ROT13](https://en.wikipedia.org/wiki/ROT13) cipher, where the values of the letters are shifted by 13 places. Thus 'A' ↔ 'N', 'B' ↔ 'O' and so on.

Write a function which takes a [ROT13](https://en.wikipedia.org/wiki/ROT13) encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [String.prototype.charCodeAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
* [String.fromCharCode()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)

## Solution

```javascript
function rot13(str) { // LBH QVQ VG!
  var strArray = str.split("");
  var newArray = [];
  for (var letter in strArray) {
    var letterCode = str.charCodeAt(letter);
    if (letterCode < 65 || letterCode > 90) {
      newArray.push(String.fromCharCode(letterCode));
    } else if (letterCode < 78) {
      newArray.push(String.fromCharCode(letterCode + 13));
    } else
      newArray.push(String.fromCharCode(letterCode - 13));
  }
  str = newArray.join("");
  return str;
}

// Change the inputs below to test
rot13("SERR PBQR PNZC");
```

## Tests

* `rot13("SERR PBQR PNZC")` should decode to `"FREE CODE CAMP"`
* `rot13("SERR CVMMN!")` should decode to `"FREE PIZZA!"`
* `rot13("SERR YBIR?")` should decode to `"FREE LOVE?"`
* `rot13("GUR DHVPX OEBJA QBT WHZCRQ BIRE GUR YNML SBK.")` should decode to `"THE QUICK BROWN DOG JUMPED OVER THE LAZY FOX."`