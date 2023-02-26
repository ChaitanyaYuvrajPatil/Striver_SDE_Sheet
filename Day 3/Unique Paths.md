

# Day 3

## Problem : Unique Paths

### Link : https://leetcode.com/problems/unique-paths/description/

## Soluton 1 (Dinamic Programming): 

```
class Solution {
public:

    int rec(int i,int j,vector<vector<int>> &dp)
    {
        if(i==0 && j==0) return 1;

        if(i<0 || j<0) return 0;

        if(dp[i][j] != -1) return dp[i][j];

        int left = rec(i-1,j,dp);
        int right = rec(i,j-1,dp);

        return dp[i][j] = left+right;
    }

    int uniquePaths(int m, int n) {
        vector<vector<int>> dp(m,vector<int>(n,-1));

        return rec(m-1,n-1,dp);
    }
};

```

## Soluton 2 (Dp tabulation): 

```
class Solution {
public:

    int rec(int i,int j,vector<vector<int>> &dp)
    {
        if(i==0 && j==0) return 1;

        if(i<0 || j<0) return 0;

        if(dp[i][j] != -1) return dp[i][j];

        int left = rec(i-1,j,dp);
        int right = rec(i,j-1,dp);

        return dp[i][j] = left+right;
    }

    int uniquePaths(int m, int n) {
       vector<vector<int>> dp(m,vector<int>(n,0));
        
        for(int i=0;i<m;i++)
        {
         for(int j=0;j<n;j++)
         {       
            if(i==0 && j==0) dp[i][j] = 1;
            else
            {
              int up = 0, left =0;
              if(i > 0)
                 up = dp[i-1][j];
              if(j > 0)
                 left = dp[i][j-1];
            
              dp[i][j] = up+left;
            }
         }
       }
        return dp[m-1][n-1];
    }
};
```


