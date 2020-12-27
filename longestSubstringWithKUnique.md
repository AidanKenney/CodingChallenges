Given a string s and an integer k, return the length of the longest substring of s that contains at most k distinct characters.

Example 1:
Input: s = "eceba", k = 2
Output: 3
Explanation: The substring is "ece" with length 3.

Example 2:
Input: s = "aa", k = 1
Output: 2
Explanation: The substring is "aa" with length 2.
 
Constraints:

1 <= s.length <= 5 * 104
0 <= k <= 50

```py
class Solution:
    def lengthOfLongestSubstringKDistinct(self, s: str, k: int) -> int:
        if k == 0 or len(s) == 0:
            return 0
        left = 0
        right = 0
        dict = {}
        max_len = 1
        while right < len(s):
            dict[s[right]] = right
            right += 1
            if len(dict) == k + 1:
                del_index = min(dict.values())
                del dict[s[del_index]]
                left = del_index + 1
            max_len = max(max_len, right - left)
        return max_len
```
