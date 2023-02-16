

# Day 2

## Problem : Missing Number

### Link : https://leetcode.com/problems/missing-number/description/

## Soluton : 

```
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int sum = 0,total = 0;
        int n = nums.size();

        for(auto it : nums) sum+=it;

        total = (n*(n+1))/2;

        return total - sum;
        
    }
};

```


