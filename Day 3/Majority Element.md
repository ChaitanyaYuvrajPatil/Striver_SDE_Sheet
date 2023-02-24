

# Day 3

## Problem : Majority Element

### Link : https://leetcode.com/problems/majority-element/description/

## Soluton 1 (using unordered map): 

```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        unordered_map<int,int>mpp;
        int n = nums.size(),mx;
        for(int i=0;i<n;i++){
            mpp[nums[i]]++;
        }
        int m= INT_MIN;
        for(auto it: mpp){
            if(it.second>m){
                m = it.second;
                mx = it.first;
            }
        }
        return mx;
    }
};
```

## Soluton 2 (Moose Voting Algorithm): 

```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int ele = 0;
        int cnt = 0;

        for(auto it : nums)
        {
            if(cnt == 0){
                ele = it;
            }
            if(it == ele)
               cnt++;
            else cnt --;
        }

        return ele;
    }
};

```


