 # Tree

+ [Symmetric-tree](#symmetric-tree)

 ## Symmetric tree

 https://leetcode.com/problems/symmetric-tree/ 

 ```python
def isSymmetric(self, root):
    return self.check_symmetry(root, root)


def check_symmetry(self, node1, node2):
    if not node1 and not node2:
        return True
    elif not node1 or not node2:
        return False

    return (node1.val == node2.val and
            self.check_symmetry(node1.left, node2.right) and
            self.check_symmetry(node1.right, node2.left))

 ```