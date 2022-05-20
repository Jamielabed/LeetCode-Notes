[Markdown Guide]([https://www.markdownguide.org/cheat-sheet])
# LeetCode Notes May 19

[Two Sum]([https://leetcode.com/problems/two-sum/])

Method:
- Look through each index in order.
- Check if target-index exists in our hashmap, if not add the index value pair to hashmap
- Keep going until you find that target-index exists in the hashmap
- Retrun the pair of the value on the hashmap and the index
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
      prevMap = {} #hash map val: index
      for i, n in enumerate(nums): #i is index and n is value
        if (target - n) in prevMap: # checking if the difference exists in map
          return [index(prevMap[target-n], i]
        prevMap[n] = i # if it isn't in the map, add current value to map and keep looking
    
    
 [Best Time to Buy and Sell Stock]([https://leetcode.com/problems/best-time-to-buy-and-sell-stock/])
 
 Method:
 - Make two pointers, left and right
 - If right - left < 0, move them both forward one index
 - else, keep moving the right pointer to the right until you find the maximim profit
'
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
    l,r = 0,1
    max = 0
    while r != len(prices):
      profit = prices[r] - prices[l]
      if profit<0:
        l += 1
        r += 1
      else:
        if profit > max:
          max = profit
'        
        
[Contains Duplicate]([https://leetcode.com/problems/contains-duplicate/])
 
Method:
- Start with an empty hash table
- Check if value at index exists in hashtable, if not, add it
- if value exists in hash table, a duplicate exists
'
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        dupMap = {} #val: index
        for i, n in enumerate(nums):
            if n in dupMap:
                return true
            else:
                dupMap[n] = i
        return false
'        
        
 
 [Product of Array Except Self]([https://leetcode.com/problems/product-of-array-except-self/])
 
 Method:
 - Create two arrays, prefix and postfix
 - prefix takes the multiplication of everything behind it starting from the left
 - postfix takes the multiplication of everything behind it starting from the right
 - the output for each index i is prefix[i-1] * postfix[i+1]


 class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * (len(nums))
        prefix = 1
        for i in range(len(nums)):
            res[i] = prefix
            prefix = prefix * nums[i]
        postfix = 1
        for i in range(len(nums) - 1, -1, -1):
            res[i] = res[i] * postfix
            postfix = postfix * nums[i]
        return res
 
 
 
 
 
 
 
 
