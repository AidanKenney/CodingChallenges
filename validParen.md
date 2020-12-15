Write a function that determines whether a string of parentheses is valid.

Examples: 
Input'()', Output: True 
Input: ')(',  Output: False
Input: "(()((())))", Output: True

```py
def valid_paren (str):
  if len(str) % 2 != 0:
    return False

  open = 0

  for char in str:
    if char == '(':
      open += 1
    elif open == 0 and char == ')':
      return False
    elif char == ')':
      open -= 1
    
  return open == 0
  ```
