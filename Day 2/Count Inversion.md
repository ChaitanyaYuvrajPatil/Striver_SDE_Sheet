

# Day 2

## Problem : Count Inversion

### Link : https://www.codingninjas.com/codestudio/problems/count-inversions_615?leftPanelTab=0

## Soluton 1 (using policy based data structures): 

```
#include <bits/stdc++.h>

#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>

using namespace std;
using namespace __gnu_pbds;

typedef tree<long long, null_type, less<long long>, rb_tree_tag,
             tree_order_statistics_node_update>
    PBDS;
long long getInversions(long long *a, int n){
    
    PBDS st;
    

    long long inversion_cnt = 0;

    for (long long i = 0; i < n; i++)
    {
        inversion_cnt += (st.size() - st.order_of_key(a[i]));
        st.insert(a[i]);
    }

    return  inversion_cnt;
}

```

## Soluton 2 (Merge sort): 

```
#include <bits/stdc++.h>

long long merge(long long arr[],long long temp[],long long left, long long mid,long long right)
{
    long long inv_cnt = 0;
    long long i = left, j=mid,k=left;

    while((i <= mid-1) && (j<= right))
    {
        if(arr[i] <= arr[j]){
            temp[k++] = arr[i++];
        }
        else{
            temp[k++] = arr[j++];
            inv_cnt += (mid-i);
        }
    }

    while(i <= mid - 1)
        temp[k++] = arr[i++];

    while(j <= right)
        temp[k++] = arr[j++];

    for(i = left ; i <= right ; i++)
        arr[i] = temp[i];
    
    return inv_cnt;
}


long long merge_sort(long long arr[],long long temp[],long long left, long long right)
{
    long long mid,inv_cnt = 0;

    if(left<right)
    {
        mid = (left+right)/2;

        inv_cnt += merge_sort(arr,temp,left,mid);
        inv_cnt += merge_sort(arr,temp,mid+1,right);

        inv_cnt += merge(arr,temp,left,mid+1,right);
    }

    return inv_cnt;
}

long long getInversions(long long *a, int n){

    long long temp[n];
    long long ans = merge_sort(a,temp,0,n-1);
    return  ans;
}
```


