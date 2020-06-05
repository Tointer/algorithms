 # Tree

+ [Subtree-of-another-tree](#subtree-of-another-tree)

 ## Subtree of another tree

 https://leetcode.com/problems/subtree-of-another-tree/ 

 ```python
def isSubtree(self, s, t):
    if not s:
        return False
    if self.isSameTree(s, t):
        return True
    return (self.isSubtree(s.left, t) or
            self.isSubtree(s.right, t))


def isSameTree(self, p, q):
    if not p and not q:
        return True
    return ((p and q) and
            p.val == q.val and
            self.isSameTree(p.right, q.right) and
            self.isSameTree(p.left, q.left))

 ```