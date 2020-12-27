Given two strings s and t, return true if they are both one edit distance apart, otherwise return false.

A string s is said to be one distance apart from a string t if you can:

Insert exactly one character into s to get t.
Delete exactly one character from s to get t.
Replace exactly one character of s with a different character to get t.
 
Example 1:
Input: s = "ab", t = "acb"
Output: true
Explanation: We can insert 'c' into s to get t.

Example 2:
Input: s = "", t = ""
Output: false
Explanation: We cannot get t from s by only one step.

Example 3:
Input: s = "a", t = ""
Output: true

Example 4:
Input: s = "", t = "A"
Output: true
 
Constraints:

0 <= s.length <= 104
0 <= t.length <= 104
s and t consist of lower-case letters, upper-case letters and/or digits.

```py
class Solution:
    def isOneEditDistance(self, s: str, t: str) -> bool:
        if len(s) == len(t):
            for i, char in enumerate(s):
                if t[i] != char:
                # if they are the same length, s and t need to be the same other than char at index where they differ
                    return (s[:i] + s[(i+1):]) == (t[:i] + t[(i+1):])
        else:
            longer = s if len(s) > len(t) else t
            shorter = s if len(s) < len(t) else t
            if len(longer) == 1 and len(shorter) == 0:
                return True
            for i, char in enumerate(longer):
                if i == len(shorter) or shorter[i] != char:
                    return (longer[:i] + longer[(i+1):]) == shorter
```
