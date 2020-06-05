 # Tree

+ [Validate-binary-search-tree](#validate-binary-search-tree)

 ## Validate binary search tree

 https://leetcode.com/problems/validate-binary-search-tree/ 

 ```python
def isValidBST(self, root):
    a = self.is_valid_recursive(root)
    if a is None:
        return False
    return True


def is_valid_recursive(self, root):
    if not root:
        return 2147483649, -2147483649
    if root.left and root.left.val >= root.val:
        return
    if root.right and root.right.val <= root.val:
        return
    if not root.right and not root.left:
        return root.val, root.val

    left = self.is_valid_recursive(root.left)
    right = self.is_valid_recursive(root.right)
    if left is None or right is None:
        return None
    min1, max1 = left
    min2, max2 = right
    if min2 <= root.val:
        return None
    if max1 >= root.val:
        return None
    return min(min1, min2), max(max1, max2)
    
 ```