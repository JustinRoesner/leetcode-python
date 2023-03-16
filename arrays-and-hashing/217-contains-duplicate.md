## 217 Contains Duplicate

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct. 

true = yes has a duplicate value.
false = every element is distinct.

---

the brute force solution:

checking each number against every other number so the 
big O time complexity would be O(n^2) n being the length of the array.
The space complexity would be O(1).

---

the solution using a hashmap:

time: O(n)

space: O(n)    because could take up as much space as original array


```
class Solution:
	def containsDuplicate(self, nums: List[int]) -> bool:
		hashset = set()
		for n in nums:
			if n in hashset:
				return True
			hashset.add(n)
		return False
```