# Find the Longest Word in a String

## Problem

Return the length of the longest word in the provided sentence.

Your response should be a number.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [String.prototype.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
* [String.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)

## Solution

```javascript
function findLongestWord(str) {
  // Create array arr of all words in the string
  var arr = str.split(" ");
  // Declare the first word the longest word
  var longestWord = arr[0];
  //Check each word's length to see if it is longer than longestWord
  for (i = 0; i < arr.length; i++) {
    if (arr[i].length > longestWord.length) {
      //If new word is longer, declare it longestWord
      longestWord = arr[i];
    }
  } return longestWord.length;
}

findLongestWord("The quick brown fox jumped over the lazy dog");
```

## Tests

* `findLongestWord("The quick brown fox jumped over the lazy dog")` should return a number.
* `findLongestWord("The quick brown fox jumped over the lazy dog")` should return 6.
* `findLongestWord("May the force be with you")` should return 5.
* `findLongestWord("Google do a barrel roll")` should return 6.
* `findLongestWord("What is the average airspeed velocity of an unladen swallow")` should return 8.
* `findLongestWord("What if we try a super-long word such as otorhinolaryngology")` should return 19.