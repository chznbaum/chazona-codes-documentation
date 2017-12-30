# Roman Numeral Converter

## Problem

Convert the given number into a roman numeral.

All [roman numerals](http://www.mathsisfun.com/roman-numerals.html) answers should be provided in upper-case.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Roman Numerals](http://www.mathsisfun.com/roman-numerals.html)
* [Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
* [Array.prototype.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
* [Array.prototype.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

## Solution

```javascript
function romanNumeralConversions(number, numeral1, numeral2, numeral3) {
  var newNum;
  if (number < 4) {
    newNum = numeral1.repeat(number);
  } else if (number == 4) {
    newNum = numeral1 + numeral2;
  } else if (number == 5) {
    newNum = numeral2;
  } else if (number > 5 && number < 9) {
    newNum = numeral2 + numeral1.repeat(number - 5);
  } else if (number == 9) {
    newNum = numeral1 + numeral3;
  }
  return newNum;
}
function finalConversion(number, numeral) {
  var newNum;
  if (number < 4) {
    newNum = numeral.repeat(number);
  }
  return newNum;
}
var temp;
function convertToRoman(num) {
  num = num.toString();
  var numArray = num.split("");
  var romanNumerals = [];
  temp = parseInt(numArray.splice(-1, 1));
  romanNumerals.unshift(romanNumeralConversions(temp, "I", "V", "X"));
  if (numArray.length !== 0) {
    temp = parseInt(numArray.splice(-1, 1));
    romanNumerals.unshift(romanNumeralConversions(temp, "X", "L", "C"));
  }
  if (numArray.length !== 0) {
    temp = parseInt(numArray.splice(-1, 1));
    romanNumerals.unshift(romanNumeralConversions(temp, "C", "D", "M"));
  }
  if (numArray.length !== 0) {
    temp = parseInt(numArray.splice(-1, 1));
    romanNumerals.unshift(finalConversion(temp, "M"));
  }
  num = romanNumerals.join("");
 return num;
}

convertToRoman(36);

```

## Tests

* `convertToRoman(2)` should return "II".
* `convertToRoman(3)` should return "III".
* `convertToRoman(4)` should return "IV".
* `convertToRoman(5)` should return "V".
* `convertToRoman(9)` should return "IX".
* `convertToRoman(12)` should return "XII".
* `convertToRoman(16)` should return "XVI".
* `convertToRoman(29)` should return "XXIX".
* `convertToRoman(44)` should return "XLIV".
* `convertToRoman(45)` should return "XLV"
* `convertToRoman(68)` should return "LXVIII"
* `convertToRoman(83)` should return "LXXXIII"
* `convertToRoman(97)` should return "XCVII"
* `convertToRoman(99)` should return "XCIX"
* `convertToRoman(500)` should return "D"
* `convertToRoman(501)` should return "DI"
* `convertToRoman(649)` should return "DCXLIX"
* `convertToRoman(798)` should return "DCCXCVIII"
* `convertToRoman(891)` should return "DCCCXCI"
* `convertToRoman(1000)` should return "M"
* `convertToRoman(1004)` should return "MIV"
* `convertToRoman(1006)` should return "MVI"
* `convertToRoman(1023)` should return "MXXIII"
* `convertToRoman(2014)` should return "MMXIV"
* `convertToRoman(3999)` should return "MMMCMXCIX"