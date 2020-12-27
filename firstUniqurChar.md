Given a string, find the first non-repeating character in it and return its index. If it doesn't exist, return -1.

Examples:
s = "leetcode"
return 0.

s = "loveleetcode"
return 2.
 
Note: You may assume the string contains only lowercase English letters.
```py
class Solution:
    def firstUniqChar(self, s: str) -> int:
        dict = {}
        for char in s:
            if char not in dict:
                dict[char] = 1
            else:
                dict[char] += 1
        for i, char in enumerate(s):
            if dict[char] == 1:
                return i
        return -1
```
