 # Linked List

+ [Reorder-list](#reorder-list)

 ## Reorder list

 https://leetcode.com/problems/reorder-list/ 

 ```python
class Solution(object):
    def reorderList(self, head):
        if not head:
            return
        if not head.next:
            return
        firstPartCur = head
        secondPartCur = self.reverseList(self.middleNode(head))
        while secondPartCur.next and firstPartCur.next:
            buf = firstPartCur.next
            firstPartCur.next = secondPartCur
            firstPartCur = secondPartCur
            secondPartCur = buf


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


    def reverseList(self, head):
        if head is None or head.next is None:
            return head

        endNode = self.reverseList(head.next)
        head.next.next = head
        head.next = None
        return endNode

 ```