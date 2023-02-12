
# Day 1

## Problem : Next Permutation

### Link : https://leetcode.com/problems/next-permutation/description/

## Soluton : 

```
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        int sz = nums.size(),k,l;
        
        for(k = sz-2;k>=0;k--){
            if(nums[k] < nums[k+1]) break;
        }

        if(k<0){
            reverse(nums.begin(),nums.end());
        }else{
            
            for(l = sz-1; l>k;l--){
                if(nums[l] > nums[k]) break;
            }

            swap(nums[k],nums[l]);
            reverse(nums.begin()+k+1,nums.end());
        }
        
    }
};


```



