This function returns an array of all combinations of the given letters
Input type: Array of single characters

Example: ['a', 'b', 'c'] returns 
[
   'a',   'b',   'ab',
  'abc', 'c',   'ac',
  'acb', 'ba',  'bac',
  'bc',  'bca', 'ca',
  'cab', 'cb',  'cba'
]

```js
function letterCombinations(arr){
     // empty solution for 'seed'
    let result = []
    // depth of the tree is the length of the array, # of chars
    let depth = arr.length
    // 4 args, arr of letters, result arr, prefix, and depth (tracks how many times we recurse)
    function addLetters(arr, result, prefix, depth) {
      // basecase
      if (depth === 1) {
      arr.forEach(x => {
        // make sure prefix does not include x, because we don't want to repeat characters
        if (!prefix.includes(x)) {
          // push the prefix, the last combo
          result.push(prefix)
          // add each char in arr to new combo, push into result
          result.push(prefix + x)
          }
        })
      } else {
        arr.forEach(x => {
          // if result does not already contain char, push it in (need to do to add single chars)
          if (!result.includes(x)){
            result.push(x)
          }
          // if the prefix passed in does not already contain char in arr...
          if (!prefix.includes(x)) {
            // invoke addLetters again with this new combo as the prefix
            addLetters(arr, result, prefix + x, depth - 1)
          }
        }) 
      }
    }
  addLetters(arr, result, '', depth)
  return result
}
```
