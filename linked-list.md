 # Linked List

+ [Intersection-of-two-linked-lists](#intersection-of-two-linked-lists)

 ## Intersection of two linked lists

 https://leetcode.com/problems/intersection-of-two-linked-lists/ 

 ```python
def getIntersectionNode(self, headA, headB):
    if not headA:
        return None
    if not headB:
        return None
    firstCur = headA
    secondCur = headB
    firstCount = 0
    secondCount = 0

    while firstCur.next:
        firstCur = firstCur.next
        firstCount += 1

    while secondCur.next:
        secondCur = secondCur.next
        secondCount += 1

    difference = firstCount - secondCount
    firstCur = headA
    secondCur = headB

    if difference < 0:
        for i in range(-difference):
            secondCur = secondCur.next
    else:
        for i in range(difference):
            firstCur = firstCur.next

    if firstCur == secondCur:
        return firstCur

    while firstCur.next:
        firstCur = firstCur.next
        secondCur = secondCur.next
        if firstCur == secondCur:
            return firstCur

    return None

 ```