 # Arrays

+ [Two-sum](#two-sum)

 ## Two-sum

 https://leetcode.com/problems/two-sum/ 

 ```python
def twoSum(self, nums, target):
    numsSet = dict()
    for num in nums:
        if numsSet.get(num) is None:
            numsSet[num] = False
        else:
            numsSet[num] = True

    for i in range(len(nums)):
        if target/2 == nums[i]:
            if not numsSet[target / 2]:
                continue
            else:
                return [i, [i for i, n in enumerate(nums) if n == target / 2][1]]

        adding = target - nums[i]
        if adding in numsSet:
            return [i, nums.index(adding)]
    return [-999, -999]


def is_overlapping(self, first_interval, second_interval):
    if first_interval[0] > second_interval[0]:
        if first_interval[0] > second_interval[1]:
            return False
    elif second_interval[0] > first_interval[1]:
        return False
    return True
 ```