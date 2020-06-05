 # Tree

+ [Same-tree](#same-tree)

 ## Same-tree

 https://leetcode.com/problems/same-tree/ 

 ```python
def isSameTree(self, p, q):
    if not p and not q:
        return True
    return ((p and q) and
            p.val == q.val and
            self.isSameTree(p.right, q.right) and
            self.isSameTree(p.left, q.left))

 ```