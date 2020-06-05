 # Tree

+ [Binary-tree-level-order-traversal](#binary-tree-level-order-traversal)

 ## Binary tree level order traversal

 https://leetcode.com/problems/binary-tree-level-order-traversal/ 

 ```python
def levelOrder(self, root):
    result = []
    return self.level_order_recursive(root, 0, result)


def level_order_recursive(self, root, depth, array):
    if not root:
        return
    if len(array) <= depth:
        array.append([root.val])
    else:
        array[depth].append(root.val)

    self.level_order_recursive(root.left, depth+1, array)
    self.level_order_recursive(root.right, depth+1, array)

    return array

 ```