 # Linked List

+ [Remove-nth-node-from-end-of-list](#remove-nth-node-from-end-of-list)

 ## Remove nth node from end of list

 https://leetcode.com/problems/remove-nth-node-from-end-of-list/ 

 ```python
def removeNthFromEnd(self, head, n):
    if not head.next:
        return None
    fastPointer = head
    latePointer = head
    for i in range(n):
        fastPointer = fastPointer.next
        if not fastPointer:
            return head.next
    while(fastPointer.next):
        fastPointer = fastPointer.next
        latePointer = latePointer.next

    latePointer.next = latePointer.next.next
    return head

 ```