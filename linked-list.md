 # Linked List

+ [Linked-list-cycle-II](#linked-list-cycle-ii)

 ## Linked list cycle II

 https://leetcode.com/problems/linked-list-cycle-ii/ 

 ```python
def detectCycle(self, head):
    if not head or not head.next:
        return None
    if head.next == head:
        return head

    fast = head.next
    slow = head

    while fast and fast.next:
        if fast != slow:
            slow = slow.next
            fast = fast.next.next
        else:
            slow = head
            while slow != fast.next:
                slow = slow.next
                fast = fast.next
            return slow
    return None



 ```