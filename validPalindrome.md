Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

Note: For the purpose of this problem, we define empty string as valid palindrome.

Example 1:
Input: "A man, a plan, a canal: Panama"
Output: true

Example 2:
Input: "race a car"
Output: false
 
Constraints:

s consists only of printable ASCII characters.
```py
import re
class Solution:
    def isPalindrome(self, s: str) -> bool:
        s= re.sub(r'[^a-zA-Z0-9]', '', s) 
        left = 0
        right = len(s) - 1
        while left <= right:
            if s[left].lower() != s[right].lower():
                    return False
            left += 1
            right -= 1
        return True
```
