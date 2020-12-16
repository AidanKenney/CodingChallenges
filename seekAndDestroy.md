You will be provided with an initial array (the first argument in the destroyer function), followed by _one or more_ arguments.

Remove all elements from the initial array that are of the same value as these arguments.

e.g.
```js
seekAndDestroy([1, 2, 3, 1, 2, 3], 2, 3) // [1,1]
seekAndDestroy([1, 2, 3, 5, 1, 2, 3], 2, 3) // [1, 5, 1]
seekAndDestroy(["tea kettle", "frog", "cloud city", 12, "bluebird", "potatoes", 92, 65, "molasses", "lullaby", "barge"], "barge", "frog", "cloud city", "bluebird", "potatoes", "molasses", "lullaby" ) // ["teakettle", 12, 92, 65]
```

```js
function seekAndDestroy(arr, ...args) {
  for (let i = 0; i < arr.length; i++) {
    if (args.includes(arr[i])) {
      arr.splice(i, 1)
      i = i - 1
    }
  }
  return arr
}
```
