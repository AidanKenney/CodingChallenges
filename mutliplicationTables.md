Write a function that returns a 2D array that represents a multiplication table from 1 through a given integer.

e.g.

```
given an argument of 3:

1 2 3
2 4 6
3 6 9
```
```js
generateMultiplicationTable(3) // [[1,2,3],[2,4,6],[3,6,9]]
generateMultiplicationTable(5) // [[1,2,3,4,5],[2,4,6,8,10],[3,6,9,12,15],[4,8,12,16,20],[5,10,15,20,25]]
```

Bonus for printing to the console in the format shown in the first example.

```js
function generateMultiplicationTable(int) {
  let table = []
  for (let i = 1; i <= int; i++) {
    let row = []
    for (let j = 1; j <= int; j++) {
      row.push(i * j)
    }
    table.push(row)
  }
  table.forEach(row => console.log(...row))
}
```
