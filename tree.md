 # Tree

+ [Binary-tree-inorder-traversal](#binary-tree-inorder-traversal)

 ## Binary tree inorder traversal

 https://leetcode.com/problems/binary-tree-inorder-traversal/ 

 ```python
def inorderTraversal(self, root):
    array = []
    self.inorderTraversalRec(root, array)
    return array


def inorderTraversalRec(self, node, array):
    if not node:
        return
    self.inorderTraversalRec(node.left, array)
    array.append(node.val)
    self.inorderTraversalRec(node.right, array)


 ```