# Everything Be True

## Problem

Check if the predicate (second argument) is truthy on all elements of a collection (first argument).

Remember, you can access object properties through either dot notation or [] notation.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

## Solution

```javascript
function truthCheck(collection, pre) {
  // Is everyone being true?
  var itemArray = [];
  var secondArray = [];
  for (var item in collection) {
    if (!collection[item].hasOwnProperty(pre)) {
      return false;
    } else
      itemArray.push(collection[item][pre]);
  }
  for (var value in itemArray) {
    if (itemArray[value] === false) {
      return false;
    } else
      secondArray.push(itemArray[value]);
  }
  for (var answer in secondArray) {
    if (secondArray[answer] === 0 || secondArray[answer] === "" || secondArray[answer] === undefined || secondArray[answer] === null || Number.isNaN(secondArray[answer])) {
      return false;
    }
  }
  pre = true;
  return pre;
}

truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex");
```

## Tests

* `truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex")` should return true.
* `truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex")` should return false.
* `truthCheck([{"user": "Tinky-Winky", "sex": "male", "age": 0}, {"user": "Dipsy", "sex": "male", "age": 3}, {"user": "Laa-Laa", "sex": "female", "age": 5}, {"user": "Po", "sex": "female", "age": 4}], "age")` should return false.
* `truthCheck([{"name": "Pete", "onBoat": true}, {"name": "Repeat", "onBoat": true}, {"name": "FastFoward", "onBoat": null}], "onBoat")` should return false
* `truthCheck([{"name": "Pete", "onBoat": true}, {"name": "Repeat", "onBoat": true, "alias": "Repete"}, {"name": "FastFoward", "onBoat": true}], "onBoat")` should return true
* `truthCheck([{"single": "yes"}], "single")` should return true
* `truthCheck([{"single": ""}, {"single": "double"}], "single")` should return false
* `truthCheck([{"single": "double"}, {"single": undefined}], "single")` should return false
* `truthCheck([{"single": "double"}, {"single": NaN}], "single")` should return false