 # Linked List

+ [Palindrome-linked-list](#palindrome-linked-list)

 ## Palindrome linked list

 https://leetcode.com/problems/palindrome-linked-list/ 

 ```python
def isPalindrome(self, head):
    if not head:
        return True
    return self.isPalindrome_(head, head)

def isPalindrome_(self, moving_node, start_node):
    comparison = False
    if moving_node and moving_node.next:
        comparison = self.isPalindrome_(moving_node.next, start_node)
        if not comparison:
            return False
        comparison = moving_node.val == start_node.next.val
        start_node.next = start_node.next.next
        return comparison
    else:
        return moving_node.val == start_node.val

 ```