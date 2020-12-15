From a sorted array of integers in ascending order, return the longest sequence of contiguous integers. 

Example: input of [1, 2, 3, 4, 7, 8, 9] should return [1, 2, 3, 4]

```py
def longest_consecutive_list(list):
  num_dict = {}
  last_num = list[0]
  index = 0
  for i, num in enumerate(list):
    if num != last_num + 1:
      index = i
      num_dict[i] = 1
      last_num = num
    elif num == last_num + 1:
      num_dict[index] += 1
      last_num = num
  keymax = max(num_dict, key = lambda x: num_dict[x])
  return list[keymax : keymax + num_dict[keymax]]
  ```
  
  Save the index where a contiguous sequence begins as the key of a dictionary, and increase it's value as a counter everytime the next number is last_num + 1. 
  If the next number is not last_num + 1, restart the process with this current index as a new key in the dictionary. 
  Find the key with the largest value (highest count of sequential numbers), and return the list from this index to the end of the sequence with slice notation. 
  O(N) time complexity.
