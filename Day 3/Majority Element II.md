

# Day 3

## Problem : Majority Element II

### Link : https://leetcode.com/problems/majority-element-ii/description/

## Soluton 1 (using unordered map): 

```
class Solution {
public:
    vector<int> majorityElement(vector<int>& nums) {
        unordered_map<int,int>mpp;
        vector<int>vec;
        int fl = floor(nums.size()/3);

        for(auto it:nums){
            mpp[it]++;
        }

        for(auto it:mpp){
            if(it.second > fl){
                vec.push_back(it.first);
            }
        }

        return vec;
    }
};
```

## Soluton 2 (Boyer Moose Voting Algorithm): 

```
class Solution {
public:
    vector<int> majorityElement(vector<int>& nums) {
       vector<int>ans;
       int num1 = -1,num2=-1;
       int c1 = 0,c2 = 0;
       int fl = floor(nums.size()/3);

       for(auto it : nums)
       {
           if(it == num1) c1++;
           else if(it == num2) c2++;
           else if(c1 == 0){
               num1 = it;
               c1 = 1;
           }
           else if(c2 == 0){
               num2 = it;
               c2 = 1;
           }
           else{
               c1--;
               c2--;
           }
       }
       c1 = 0;
       c2 = 0;

       for(auto it : nums)
       {
           if(it == num1) c1++;
           else if(it == num2) c2++;
       }

       if(c1>fl) ans.push_back(num1);
       if(c2>fl) ans.push_back(num2);

       return ans;
    }
};
```


