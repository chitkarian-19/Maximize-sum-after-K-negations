# Maximize-sum-after-K-negations
Maximize sum after K negations
 
```cpp
class Solution {

    public static long maximizeSum(long arr[], int n, int k)
    {
        Arrays.sort(arr);
        
        long minVal = Long.MAX_VALUE;
        int minIndex = 0;
        for(int i=0;i<n;i++){
            if(arr[i]<0){
                
                if(k>0){
                    k--;
                    arr[i]=-1*arr[i];
                }
                 
            }
            if(minVal>arr[i]){
                minVal = arr[i];
                minIndex = i;
            }
        }
        
        if(k%2!=0)
        arr[minIndex]=-1*arr[minIndex];
        long sum =0;
        for(int i=0;i<n;i++){
            sum+=arr[i];
        }
        return sum;
        
    }
}

```

Time Complexity : O(n)

Space Complexity : O(1)
