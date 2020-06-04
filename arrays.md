 # Arrays

+ [Subarray-sum-equals-k](#subarray-sum-equals-k)

 ## Subarray-sum-equals-k

 https://leetcode.com/problems/subarray-sum-equals-k/ 

 ```python
def subarraySum(self, nums, k):
    table = {0: 1}
    summ = 0
    answer = 0
    for i in range(len(nums)):
        summ += nums[i]
        if summ - k in table:
            answer += table[summ - k]
        if summ in table:
            table[summ] += 1
        else:
            table[summ] = 1
    return answer
    
 ```