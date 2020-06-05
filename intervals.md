 # Intervals

+ [Insert-interval](#insert-interval)

 ## Insert-interval

 https://leetcode.com/problems/insert-interval/ 

 ```python
def insert(self, intervals, newInterval):
    intervals.append(newInterval)
    intervals.sort()
    result = []
    i = 0
    while i < len(intervals):
        if not result or result[-1][1]<intervals[i][0]: result.append(intervals[i])
        if result[-1][0]<=intervals[i][0]<=result[-1][1]:
            result[-1][1] = intervals[i][1] if result[-1][1] <= intervals[i][1] else result[-1][1]
        i+=1
    return result
 ```