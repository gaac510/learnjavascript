### [Link: freeCodeCamp project challenge - Cash Register](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/cash-register)

My solution:
```js
function checkCashRegister(price, cash, cid) {
  const pricePenny = Math.round(price*100);
  const cashPenny = Math.round(cash*100);
  const cidPenny = cid.map( x => [ x[0], Math.round(x[1]*100) ] );

  const insufficientFunds = {status: "INSUFFICIENT_FUNDS", change: []};
  const closedResult = {status: "CLOSED", change: cid}
  const changeResult = {status: "OPEN", change: []};
  const cidTotal = cidPenny.map(x => x[1]).reduce((a, c) => a + c);

  let changeAmount = cashPenny - pricePenny;
  
  if (changeAmount === cidTotal) {
    return closedResult;
  };

  const pennyTable = {
    "PENNY": 1,
    "NICKEL": 5,
    "DIME": 10,
    "QUARTER": 25,
    "ONE": 100,
    "FIVE": 500,
    "TEN": 1000,
    "TWENTY": 2000,
    "ONE HUNDRED": 10000
  };

  for (let i = cidPenny.length - 1, remainder = 0; i >= 0; i--) {
    if (cidPenny[i][1] < changeAmount) {
      changeResult.change.push(cid[i])
      changeAmount = changeAmount - cidPenny[i][1]
    } else {
      remainder = changeAmount % pennyTable[cid[i][0]];
      if (changeAmount - remainder !== 0) {
        changeResult.change.push([cid[i][0], (changeAmount - remainder)/100])
      };
      changeAmount = remainder;
    };    
  };

  if (changeAmount > 0) {
    return insufficientFunds;
  };
  
  return changeResult;
}

//Test
console.log(checkCashRegister(3.26, 100, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]));
```
