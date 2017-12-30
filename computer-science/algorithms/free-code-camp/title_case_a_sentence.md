# Title Case a Sentence

## Problem

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [String.prototype.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)


## Solution

```javascript
function titleCase(str) {
  // Make the string lowercase
  str = str.toLowerCase();
  // Split the string into words, and the words into letters
  var strArray = str.split(" ");
  var newArray = [];
  for (i = 0; i < strArray.length; i++) {
    strArray[i] = strArray[i].split("");
    // Capitalize the first letter in each word
    strArray[i][0] = strArray[i][0].toUpperCase();
    // Put the letters back together into words
    newArray.push(strArray[i].join(""));
  }
  // Put the words back together into a string
  var newStr = newArray.join(" ");
  return newStr;
}
titleCase("I'm a little tea pot");
```