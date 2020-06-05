 # Tree

+ [Kth-smallest-element-in-a-bst](#kth-smallest-element-in-a-bst)

 ## Kth smallest element in a bst

 https://leetcode.com/problems/kth-smallest-element-in-a-bst/ 

 ```python
def kthSmallest(self, root, k):
    array = []
    self.kth_smallest_recursive(root, k, array)
    return array[0]


def kth_smallest_recursive(self, root, k, result):
    if not root:
        return k
    if not root.left and not root.right:
        if k == 1:
            result.append(root.val)
            return None
        else:
            return k-1
    if len(result) == 1:
        return None

    left = self.kth_smallest_recursive(root.left, k, result)
    if left is None:
        return None
    if left == 1:
        result.append(root.val)
        return None

    return self.kth_smallest_recursive(root.right, left-1, result)

 ```