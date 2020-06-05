 # Tree

+ [Binary-search-tree-iterator](#binary-search-tree-iterator)

 ## Binary search tree iterator

 https://leetcode.com/problems/binary-search-tree-iterator/ 

 ```python
class BSTIterator:
    def __init__(self, root):
        inorder = self.levelOrder(root)
        self.flat_list = []
        for sublist in inorder:
            for item in sublist:
                self.flat_list.append(item)
        self.flat_list.sort()
        self.i = 0

    def next(self):
        self.i += 1
        return self.flat_list[self.i - 1]

    def hasNext(self):
        return self.i != len(self.flat_list)

    def levelOrder(self, root):
        result = []
        self.level_order_recursive(root, 0, result)
        return result

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