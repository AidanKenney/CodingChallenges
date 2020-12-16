One of the simplest and most widely known ciphers is a Caesar cipher, also known as a shift cipher. In a shift cipher the meanings of the letters are shifted by some set amount.

A common modern use is the ROT13 cipher, where the values of the letters are shifted by 13 places. Thus 'A' <=> 'N', 'B' <=> 'O' and so on.

Write a function which takes a ROT13 encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.

e.g.
```js
rot13("URYYB JQV FRNGGYR!") // "HELLO WDI SEATTLE"
rot13("CBGNGBRF NAQ ZBYNFFRF") // "POTATOES AND MOLASSES"
rot13("VS LBHE FGBZNPU VF TEHZOYVA' NAQ LBHE ZBHGU FGNEGF N-ZHZOYVA'") // "IF YOUR STOMACH IS GRUMBLIN' AND YOUR MOUTH STARTS A-MUMBLIN'"
```

```js
function rot13(FGE) {
  const alpha = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
  let blankString = ''
  const newLetter = (newIndex) => {
    if (newIndex < 13) {
      return alpha[newIndex + 13]
    } else {
      return alpha[newIndex - 13]
    }
  }
  for (let i = 0; i < FGE.length; i++) {
    if (alpha.includes(FGE[i])) {
      const newIndex = alpha.indexOf(FGE[i])
      blankString += newLetter(newIndex)
    } else {
      blankString += FGE[i]
    }
  }
  return blankString
}
```
