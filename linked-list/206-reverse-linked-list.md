## 206 Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

Given the head of a singly linked list, reverse the list, and return the reversed list.

---

time: O(n) 

space: O(1) 

```
class Solution:
	def reverseList(self, head: ListNode) -> ListNode:
		previous = None
		current = head

		while current:
			tempNext = current.next
			current.next = previous
			previous = current
			current = tempNext
		return previous
```