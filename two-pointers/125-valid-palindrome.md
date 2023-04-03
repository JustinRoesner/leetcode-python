## 125 Valid Palindrome 

https://leetcode.com/problems/valid-palindrome/

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

---

time: O(n) 

space: O(1) 

```
class Solution:
	def isPalindrome(self, s: str) -> bool:
		l = 0
		r = len(s) - 1

		while l < r:
			while l < r and not s[l].isalnum():
				l += 1
			while l < r and not s[r].isalnum():
				r -= 1

			if s[l].lower() != s[r].lower():
				return False
			else:
				l += 1
				r -= 1
	return True
```