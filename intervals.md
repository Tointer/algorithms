 # Intervals

+ [Merge-intervals](#merge-intervals)

 ## Merge-intervals

 https://leetcode.com/problems/merge-intervals/ 

 ```python
def merge(self, intervals):
    if not intervals:
        return []
    intervals.sort()
    result = [intervals[0]]

    for i in range(len(intervals)):
        if self.is_overlapping(result[-1], intervals[i]):
            result[-1][0] = min(result[-1][0], intervals[i][0])
            result[-1][1] = max(result[-1][1], intervals[i][1])
        else:
            result.append(intervals[i])

    return result


def is_overlapping(self, first_interval, second_interval):
    if first_interval[0] > second_interval[0]:
        if first_interval[0] > second_interval[1]:
            return False
    elif second_interval[0] > first_interval[1]:
        return False
    return True

 ```