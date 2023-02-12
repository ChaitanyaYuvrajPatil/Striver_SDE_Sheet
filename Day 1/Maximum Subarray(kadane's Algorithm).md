
# Day 1

## Problem : Maximum Subarray(kadane's Algorithm)

### Link : https://leetcode.com/problems/maximum-subarray/description/

## Soluton : 

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxi = INT_MIN;
        int sum = 0;

        for(auto it : nums){
            sum += it;
            maxi = max(sum,maxi);
            if(sum<0) sum = 0;
        }

        return maxi;
    }
};


```




