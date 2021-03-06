# Leetcode-challenges

## 1. Two sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.
Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Only one valid answer exists.

```
class Solution(object):
    def twoSum(self, nums, target):
       
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
## 4. Palindrome Number
Given an integer x, return true if x is palindrome integer.
```
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        return str(x) == str(x)[::-1]
            
```

## 5. Longest Common Prefix
Write a function to find the longest common prefix string amongst an array of strings.
If there is no common prefix, return an empty string "".
```
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        dict_prefix = {}
        list_substr = []

        count_max = len(max(strs, key=len))

        for count in range(0, count_max):
            for word in strs:
                dict_prefix[word[0:count+1]]= dict_prefix.get(word[0:count+1],0)+1
        #print(dict_prefix)
        for k,v in dict_prefix.items():
            if v == len(strs):
                list_substr.append(k)
        return max(list_substr)
        
```
# 6. Implement strStr()
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.
```
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        if needle in haystack:
            return haystack.index(needle)
        else:
            return 0
```
## 7. Valid Palindrome
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.
Given a string s, return true if it is a palindrome, or false otherwise.
```
class Solution(object):
    def isPalindrome(self, s):
        """
        :type s: str
        :rtype: bool
        """
        s = s.lower().replace(" ", "")
        s = ''.join(char for char in s if char.isalnum())
        return s == s[::-1]
```

 ## 8. Pandas drop rows with blanks
 ```
import pandas as pd
import numpy as np
# dictionary with list object in values
details = {
	'Name' : ['CDF', 'ABC', 'GHI', 'JKL'],
	'Age' : [23, 21, 22, 21],
	'University' : ['BHU', 'JNU', ' ', ' '],
}

# creating a Dataframe object
df = pd.DataFrame(details)

df.replace(' ',np.nan, inplace=True)

df.dropna()
```
