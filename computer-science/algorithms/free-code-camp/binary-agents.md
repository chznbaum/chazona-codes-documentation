# Binary Agents

## Problem

Return an English translated sentence of the passed binary string.

The binary string will be space separated.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [String.prototype.charCodeAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
* [String.fromCharCode()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)

## Solution

```javascript
function binaryAgent(str) {
  var binaryArray = str.split(" ");
  console.log(binaryArray);
  var code;
  var engArray = [];
  for (var item in binaryArray) {
    code = parseInt(binaryArray[item], 2);
    code = code.toString(10);
    code = String.fromCharCode(code);
    engArray.push(code);
  }
  str = engArray.join("");
  return str;
}

binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");
```

## Tests

* `binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111")` should return "Aren't bonfires fun!?"
* `binaryAgent("01001001 00100000 01101100 01101111 01110110 01100101 00100000 01000110 01110010 01100101 01100101 01000011 01101111 01100100 01100101 01000011 01100001 01101101 01110000 00100001")` should return "I love FreeCodeCamp!"