 # Linked List

+ [Reverse-linked-list](#reverse-linked-list)

 ## Reverse linked list

 https://leetcode.com/problems/reverse-linked-list/ 

 ```python
def reverseList(self, head):
    if not head or not head.next:
        return head

    endNode = self.reverseList(head.next)
    head.next.next = head
    head.next = None
    return endNode
 ```