# Exact Change

## Problem

Design a cash register drawer function `checkCashRegister()` that accepts purchase price as the first argument (`price`), payment as the second argument (`cash`), and cash-in-drawer (`cid`) as the third argument.

`cid` is a 2D array listing available currency.

Return the string `"Insufficient Funds"` if cash-in-drawer is less than the change due. Return the string `"Closed"` if cash-in-drawer is equal to the change due.

Otherwise, return change in coin and bills, sorted in highest to lowest order.

Remember to use **Read-Search-Ask** if you get stuck. Try to pair program. Write your own code.

Here are some helpful links:

* [Global Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

## Solution

```javascript
function checkCashRegister(price, cash, cid) {
  var change = [];
  // Here is your change, ma'am.
  var amountChange = cash - price;
  var drawerCash = 0;
  var amounts = [0.01, 0.05, 0.10, 0.25, 1.00, 5.00, 10.00, 20.00, 100.00];
  for (var item in cid) {
    drawerCash += cid[item][1];
  }
  if (drawerCash < amountChange) {
    return "Insufficient Funds";
  } else if (drawerCash == amountChange) {
    return "Closed";
  } else if (drawerCash > amountChange) {
    for (i = 8; i >= 0; i--) {
      var changeDivision;
      var numberOfType;
      if (amountChange >= amounts[i]) {
        switch (i) {
          case 8:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = parseInt(amountChange / 100) * 100;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["ONE HUNDRED", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 100);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 100);
                  change.push(["ONE HUNDRED", Number((numberOfType * 100).toFixed(2))]);
                }
              }
              
            }
            break;
          case 7:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = parseInt(amountChange / 20) * 20;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["TWENTY", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 20);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 20);
                  change.push(["TWENTY", Number((numberOfType * 20).toFixed(2))]);
                }
              }
              
            }
            break;
          case 6:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = parseInt(amountChange / 10) * 10;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["TEN", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 10);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 10);
                  change.push(["TEN", Number((numberOfType * 10).toFixed(2))]);
                }
              }
              
            }
            break;
          case 5:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = parseInt(amountChange / 5) * 5;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["FIVE", Number(cid[i][1].toPrecision(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 5);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 5);
                  change.push(["FIVE", Number((numberOfType * 5).toFixed(2))]);
                }
              }
              
            }
            break;
          case 4:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = parseInt(amountChange / 1) * 1;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["ONE", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 1);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 1);
                  change.push(["ONE", Number((numberOfType * 1).toFixed(2))]);
                }
              }
              
            }
            break;
          case 3:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = amountChange / 0.25;
              changeDivision = Number(changeDivision.toFixed(2));
              changeDivision = changeDivision * 0.25;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["QUARTER", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 0.25);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 0.25);
                  change.push(["QUARTER", Number((numberOfType * 0.25).toFixed(2))]);
                }
              }
              
            }
            break;
          case 2:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = amountChange / 0.10;
              changeDivision = Number(changeDivision.toFixed(2));
              changeDivision = changeDivision * 0.10;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["DIME", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 0.10);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 0.10);
                  change.push(["DIME", Number((numberOfType * 0.10).toFixed(2))]);
                }
              }
              
            }
            break;
          case 1:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = amountChange / 0.05;
              changeDivision = Number(changeDivision.toFixed(2));
              changeDivision = changeDivision * 0.05;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["NICKEL", Number(cid[i][1].toFixed(2))]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 0.05);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 0.05);
                  change.push(["NICKEL", Number((numberOfType * 0.05).toFixed(2))]);
                }
              }
              
            }
            break;
          case 0:
            if ((amountChange >= amounts[i]) && (cid[i][1] !== 0)) {
              changeDivision = amountChange / 0.01;
              changeDivision = Number(changeDivision.toFixed(2));
              changeDivision = changeDivision * 0.01;
              if (changeDivision >= cid[i][1]) {
                amountChange = amountChange - cid[i][1];
                change.push(["PENNY", cid[i][1].toFixed(2)]);
              } else if (changeDivision < cid[i][1]){
                numberOfType = parseInt(changeDivision / 0.01);
                if (numberOfType !== 0) {
                  amountChange = amountChange - (numberOfType * 0.01);
                  change.push(["PENNY", Number((numberOfType * 0.01).toFixed(2))]);
                }
              }
              
            }
            if (amountChange > 0) {
              return "Insufficient Funds";
            }
            break;
        }
      }
    }
  }
  return change;
}

// Example cash-in-drawer array:
// [["PENNY", 1.01],
// ["NICKEL", 2.05],
// ["DIME", 3.10],
// ["QUARTER", 4.25],
// ["ONE", 90.00],
// ["FIVE", 55.00],
// ["TEN", 20.00],
// ["TWENTY", 60.00],
// ["ONE HUNDRED", 100.00]]

checkCashRegister(19.50, 20.00, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.10], ["QUARTER", 4.25], ["ONE", 90.00], ["FIVE", 55.00], ["TEN", 20.00], ["TWENTY", 60.00], ["ONE HUNDRED", 100.00]]);
```

## Tests

* `checkCashRegister(19.50, 20.00, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.10], ["QUARTER", 4.25], ["ONE", 90.00], ["FIVE", 55.00], ["TEN", 20.00], ["TWENTY", 60.00], ["ONE HUNDRED", 100.00]])` should return an array.
* `checkCashRegister(19.50, 20.00, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])` should return a string.
* `checkCashRegister(19.50, 20.00, [["PENNY", 0.50], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])` should return a string.
* `checkCashRegister(19.50, 20.00, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.10], ["QUARTER", 4.25], ["ONE", 90.00], ["FIVE", 55.00], ["TEN", 20.00], ["TWENTY", 60.00], ["ONE HUNDRED", 100.00]])` should return `[["QUARTER", 0.50]]`.
* `checkCashRegister(3.26, 100.00, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.10], ["QUARTER", 4.25], ["ONE", 90.00], ["FIVE", 55.00], ["TEN", 20.00], ["TWENTY", 60.00], ["ONE HUNDRED", 100.00]])` should return `[["TWENTY", 60.00], ["TEN", 20.00], ["FIVE", 15.00], ["ONE", 1.00], ["QUARTER", 0.50], ["DIME", 0.20], ["PENNY", 0.04]]`.
* `checkCashRegister(19.50, 20.00, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])` should return `"Insufficient Funds"`.
* `checkCashRegister(19.50, 20.00, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 1.00], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])` should return `"Insufficient Funds"`.
* `checkCashRegister(19.50, 20.00, [["PENNY", 0.50], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])` should return `"Closed"`.