 # Linked List

+ [Linked-list-cycle](#linked-list-cycle)

 ## Linked list cycle

 https://leetcode.com/problems/linked-list-cycle/ 

 ```python
def hasCycle(self, head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if fast == slow:
            return True
    return False

 ```