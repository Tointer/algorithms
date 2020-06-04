 # Tree

+ [Path-sum](#path-sum)

 ## Path sum

 https://leetcode.com/problems/path-sum/ 

 ```python
def hasPathSum(self, root, sum):
    if not root:
        return False
    if not root.left and not root.right:
        return sum == root.val

    return (self.hasPathSum(root.left, sum - root.val) or
            self.hasPathSum(root.right, sum - root.val))

 ```