# Reverse a String

## Problem

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Global String Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
* [String.prototype.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
* [Array.prototype.reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
* [Array.prototype.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

## Solution

```javascript
function reverseString(str) {
  var arr = str.split("");
  arr = arr.reverse();
  str = arr.join("");
  return str;
}

reverseString("hello");
```

## Tests

* `reverseString("hello")` should return a string.
* `reverseString("hello")` should become `"olleh"`.
* `reverseString("Howdy")` should become `"ydwoH"`.
* `reverseString("Greetings from Earth")` should return `"htraE morf sgniteerG"`.