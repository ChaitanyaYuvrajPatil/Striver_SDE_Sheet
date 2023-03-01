

# Day 4

## Problem : Two Sum

### Link : https://leetcode.com/problems/two-sum/description/

## Soluton : 

```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
       vector<int>vec;
       unordered_map<int,int> mpp;

       for(int i=0;i<nums.size();i++)
       {
           if(mpp.find(target-nums[i]) != mpp.end())
           {
               vec.emplace_back(i);
               vec.emplace_back(mpp[target-nums[i]]);
           }

           mpp[nums[i]] = i;
       }

       return vec;
    }
};

```


