 # Linked List

+ [Merge-two-sorted-lists](#merge-two-sorted-lists)

 ## Merge two sorted lists

 https://leetcode.com/problems/merge-two-sorted-lists/ 

 ```python
def mergeTwoLists(self, l1, l2):
    if not l1:
        return l2
    if not l2:
        return l1

    minTail = l1
    source = l2
    if minTail.val > l2.val:
        minTail = l2
        source = l1
    cur = minTail

    while cur.next or source:
        if source and (cur.next is None or source.val <= cur.next.val):
            buf = cur.next
            cur.next = source
            cur = source
            source = buf
        else:
            cur = cur.next

    return minTail

 ```