This function returns an array of all possible outcomes from flipping a coin N times.
For example, coinFlips(2) would return the following:
["HH", "HT", "TH", "TT"]

```js
function coinFlips(num){
    // empty solution to function as "seed"
    let result = []
    // helper function tracks current items in result and adds our 2 options: H and T
    function flipHelper(n, result, current) {
      // base case: stop running function when num === 1
      if (n === 1) {
      // add H, T to previous argument
      result.push(current + 'H')
      result.push(current + 'T')
      } else {
      // invoke function again with an additional H on current argument, same for T
      flipHelper(n - 1, result, current + 'H')
      flipHelper(n - 1, result, current + 'T')
      }
    } 
  // first call of function, with blank string as 'current'
  flipHelper(num, result, '')
  return result
}
```
