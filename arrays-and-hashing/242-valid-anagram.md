## 242 Valid Anagram

https://leetcode.com/problems/valid-anagram/

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An anagram is when two words share the same letters in the same amount in any order. 

true = yes s and t are anagrams.
false = s and t are not anagrams.

---

the solution using a hashmap:

time: O(n) 

space: O(n) 

```
class Solution:
	def isAnagram(self, s: str, t: str) -> bool:
		if len(s) != len(t):
			return False

		countSLetters, countTLetters = {}, {}

		for i in range(len(s)):
			countSLetters[s[i]] = 1 + countSLetters.get(s[i], 0)
			countTLetters[t[i]] = 1 + countTLetters.get(t[i], 0)
		return countSLetters == countTLetters
```