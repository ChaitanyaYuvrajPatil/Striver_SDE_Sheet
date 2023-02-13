
# Day 2

## Problem : Rotate Image

### Link : https://leetcode.com/problems/rotate-image/description/

## Soluton : 

```
class Solution {
public:
    void rotate(vector<vector<int>>& mat) {
        
        for(int i=0;i<mat.size();i++)
        {
            for(int j=0;j<i;j++){
                swap(mat[i][j],mat[j][i]);
            }
        }

        for(int i=0;i<mat.size();i++)
           reverse(mat[i].begin(),mat[i].end());

    }
};
```


