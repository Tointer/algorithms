 # Linked List

+ [Middle-of-the-linked-list](#middle-of-the-linked-list)

 ## Middle of the linked list

 https://leetcode.com/problems/middle-of-the-linked-list/ 

 ```python
def middleNode(self, head):
    if not head or not head.next:
        return head

    fast_cur = head
    slow_cur = head

    while fast_cur.next and fast_cur.next.next:
        fast_cur = fast_cur.next.next
        slow_cur = slow_cur.next

    if fast_cur.next:
        return slow_cur.next
    return slow_cur

 ```