Given n non-negative integers representing an elevation map where the width of each bar is 1, 
compute how much water it can trap after raining.

Example 1:
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.

Example 2:
Input: height = [4,2,0,3,2,5]
Output: 9
 
Constraints:

n == height.length
0 <= n <= 3 * 104
0 <= height[i] <= 105
```py
class Solution:
    def trap(self, height: List[int]) -> int:
        water = 0
        p1 = 0
        p2 = len(height) - 1
        # track max heights on left and right side
        # these indicate whether water can be trapped at current index, regardless of what's in between
        maxLeft = 0
        maxRight = 0
        while p1 < p2: 
            if height[p1] > height[p2]:
                if height[p2] > maxRight:
                    maxRight = height[p2]
                    p2 -= 1
                else: 
                    water += maxRight - height[p2]
                    p2 -= 1
            else: 
                if height[p1] > maxLeft:
                    maxLeft = height[p1]
                    p1 += 1
                else:
                    water += maxLeft - height[p1]
                    p1 += 1
        return water
```
