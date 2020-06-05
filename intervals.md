 # Intervals

+ [Non-overlapping Intervals](#non-overlapping-intervals)

## Non-overlapping Intervals

 https://leetcode.com/problems/non-overlapping-intervals/ 

 ```python
class Solution(object):
    def eraseOverlapIntervals(self, intervals):
        if len(intervals) <= 1:
            return 0
        
        intervals.sort(key = lambda x: x[1])
        
        prev = intervals[0]
        erased = 0
        for interval in intervals[1:]:
            if interval[0] < prev[1]:
                erased += 1
            else:
                prev = interval
            
        return erased
 ```