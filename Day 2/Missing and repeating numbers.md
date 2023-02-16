

# Day 2

## Problem : Missing and repeating numbers

### Link : https://www.codingninjas.com/codestudio/problems/873366?topList=striver-sde-sheet-problems&leftPanelTab=0

## Soluton : 

```
#include <bits/stdc++.h> 
#include <bits/stdc++.h> 

pair<int,int> missingAndRepeating(vector<int> &arr, int n)
{
	// Write your code here 

	int xor1;
	int x = 0,y=0;
	int set_bit_no;
	int i;

	xor1 = arr[0];

	for(i=1;i<n;i++) xor1 = xor1^arr[i];

	for(i=1;i<=n;i++) xor1 = xor1^i;

	set_bit_no = xor1 & ~(xor1-1);

	for(i=0;i<n;i++)
	{
		if(arr[i] & set_bit_no) x = x^ arr[i];
		else y = y^ arr[i];
	}

	for(i=1;i<=n;i++)
	{
		if(i & set_bit_no) x = x^i;
		else y = y^i;
	}

	int x_count = 0;
    for (i=0; i<n; i++) {
        if (arr[i]==x)
            x_count++;
    }
    
    if (x_count==0)
        return {x,y};
    
    return {y,x};

}


```


