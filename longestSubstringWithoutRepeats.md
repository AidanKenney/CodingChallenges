Given a string s, find the length of the longest substring without repeating characters.

Example 1:
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.

Example 2:
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.

Example 3:
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.

Example 4:
Input: s = ""
Output: 0
 
Constraints:

0 <= s.length <= 5 * 104
s consists of English letters, digits, symbols and spaces.
```py
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
    # hashmap for storing chars and index
        dict  = {}
        left = 0
        right = 0
        max_len = 0
        while right < len(s):
            if s[right] in dict:
                if dict[s[right]] >= left:
                    left = dict[s[right]] + 1
            dict[s[right]] = right
            max_len = max(max_len, (right - left) + 1)
            right += 1
        return max_len
```
