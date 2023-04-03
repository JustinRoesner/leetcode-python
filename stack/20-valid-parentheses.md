## 20 Valid Parentheses

https://leetcode.com/problems/valid-parentheses/

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.

---

Because we go through each element once and add each element to a stack.

time: O(n) 

space: O(n) 

```
class Solution:
	def isValidParentheses(self, s: str) -> bool:
		mapParen = { ")": "(", "]": "[", "}": "{" }
		stack = []

		for c in s:
			if c in mapParen:
				if stack and stack[-1] == mapParen[c]:
					stack.pop()
				else:
					return False
			else:
				stack.append(c)
		
		return not stack
```