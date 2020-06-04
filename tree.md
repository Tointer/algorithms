 # Tree

+ [Invert-binary-tree](#invert-binary-tree)

 ## Invert binary tree

 https://leetcode.com/problems/invert-binary-tree/ 

 ```python
def invertTree(self, root):
    if not root:
        return
    if not root.left and not root.right:
        return root

    self.invertTree(root.left)
    self.invertTree(root.right)

    root.left, root.right = root.right, root.left
    return root

 ```