 # Linked List

+ [Sort-list](#sort-list)

 ## Sort list

 https://leetcode.com/problems/sort-list/ 

 ```python
def split_list(self, head):
    pre, slow, fast = None, head, head
    while fast and fast.next:
        pre, slow, fast = slow, slow.next, fast.next.next
    pre.next = None
    return head, slow


def merge(self, first, second):
    if not first or not second:
        return first or second
    if first.val > second.val:
        first, second = second, first
    head = pre = first
    first = first.next
    while first and second:
        if first.val < second.val:
            pre.next = first
            first = first.next
        else:
            pre.next = second
            second = second.next
        pre = pre.next
    pre.next = first or second
    return head


def sortList(self, head):
    if not head or not head.next:
        return head
    first, second = self.split_list(head)
    first, second = self.sortList(first), self.sortList(second)
    head = self.merge(first, second)
    return head

 ```