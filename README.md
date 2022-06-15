# Leetcode-challenges

## 1. Two sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.
Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]

Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]

Constraints:

    2 <= nums.length <= 104
    -109 <= nums[i] <= 109
    -109 <= target <= 109
    Only one valid answer exists.

```
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        seen_dict = {}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in seen_dict:
                return [seen_dict[diff], i]
            seen_dict[n] = i
        return
```

## 2. Remove duplicates from list
Input: [1,1,2,3,3]
Output: [1,2,3]
```
        dict_uniq = {}
        list_uniq = []
        for num in head:
            if num not in dict_uniq:
                dict_uniq[num]=1
            else:
                dict_uniq[num]+=1
        for key in dict_uniq:
            list_uniq.append(key)
        return sorted(list_uniq)
 ```

## 3. Length of Last Word
Example 1:

Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.

```
class Solution(object):
    def lengthOfLastWord(self, s):
        """
        :type s: str
        :rtype: int
        """
     
        ls_sen = s.strip().split()
        return  len(ls_sen[len(ls_sen)-1])
        
```
