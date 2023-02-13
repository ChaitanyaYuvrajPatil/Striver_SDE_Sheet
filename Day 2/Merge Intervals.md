
# Day 2

## Problem : Merge Intervals

### Link : https://leetcode.com/problems/merge-intervals/

## Soluton : 

```
class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {
        vector<vector<int>> merging;

        if(intervals.size() == 0) return merging;

        sort(intervals.begin(),intervals.end());

        vector<int> temp = intervals[0];

        for(auto it : intervals)
        {
            if(temp[1] >= it[0])
            {
                temp[1] = max(temp[1],it[1]);
            }else{
                merging.push_back(temp);
                temp = it;
            }
        }
        merging.push_back(temp);
        return merging;
    }
};
```


