

# Day 3

## Problem : Search a 2D Matrix

### Link :https://leetcode.com/problems/search-a-2d-matrix/description/

## Soluton 1 : 

```
class Solution {
public:

    bool binarySearch(vector<int> arr, int l, int r, int x)
    {
       while (l <= r) {
           int m = l + (r - l) / 2;
     
           if (arr[m] == x)
           {
               cout<<arr[m]<<endl;
                return true;
           }
     
           if (arr[m] < x)
               l = m + 1;
  
           else
               r = m - 1;
         }
  
        return false;
   }
    bool searchMatrix(vector<vector<int>>& mat, int target) {
    
    int n = mat.size();
    int m = mat[0].size()-1;
    
    for(int i=0;i<n;i++)
    {
        if(mat[i][0]<=target && target <= mat[i][m]){
            return binarySearch(mat[i],0,m,target);         
        }
    }
    return 0;
    }
};

```

## Soluton 2 : 

```
class Solution {
public:

    bool binarySearch(vector<vector<int>>& arr, int l, int r, int x, int row)
    {
       while (l <= r) {
           int m = l + (r - l) / 2;
     
           if (arr[row][m] == x)
           {
               cout<<arr[row][m]<<endl;
                return true;
           }
     
           if (arr[row][m] < x)
               l = m + 1;
  
           else
               r = m - 1;
         }
  
        return false;
   }
    bool searchMatrix(vector<vector<int>>& mat, int target) {
    
    int n = mat.size();
    int m = mat[0].size()-1;
    
    for(int i=0;i<n;i++)
    {
        if(mat[i][0]<=target && target <= mat[i][m]){
            return binarySearch(mat,0,m,target,i);         
        }
    }
    return 0;
    }
};
```


