# Pig Latin

## Problem

Translate the provided string to pig latin.

[Pig Latin](http://en.wikipedia.org/wiki/Pig_Latin) takes the first consonant (or consonant cluster) of an English word, moves it to the end of the word and suffixes an "ay".

If a word begins with a vowel you just add "way" to the end.

Input strings are guaranteed to be English words in all lowercase.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Array.prototype.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
* [Array.prototype.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
* [Array.prototype.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
* [String.prototype.substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr)
* [String.prototype.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)

## Solution

```javascript
function translatePigLatin(str) {
  var wordArray = str.split("");
  console.log(wordArray);
  var vowels = "aeiou";
  var consonant;
  for (i = 0; i < wordArray.length; i++) {
    if (vowels.includes(wordArray[0])) {
      str = wordArray.join("");
      if (i === 0) {
        str = str + "way";
        return str;
      } else
        str = str + "ay";
      return str;
    } else
      consonant = wordArray.shift();
      wordArray.push(consonant);
  }
  return str;
}

translatePigLatin("consonant");
```

## Tests

* `translatePigLatin("california")` should return "aliforniacay".
* `translatePigLatin("paragraphs")` should return "aragraphspay".
* `translatePigLatin("glove")` should return "oveglay".
* `translatePigLatin("algorithm")` should return "algorithmway".
* `translatePigLatin("eight")` should return "eightway".