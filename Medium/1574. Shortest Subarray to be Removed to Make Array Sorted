class Solution {
    public int findLengthOfShortestSubarray(int[] arr) {
        int n=arr.length;
        int left=0,right=arr.length-1;
        while(left<n-1&&arr[left]<=arr[left+1])
        left++;
        if(left==n-1) return 0;
        while(right>0&&arr[right]>=arr[right-1])
        right--;
        int res=Math.min(right,n-left-1);
        int i=0;
        while(i<=left&&right<n)
        {
            if(arr[i]<=arr[right])
            {
                res=Math.min(res,right-i-1);
                i++;
            }
            else
            right++;
        }
        return res;
    }
}
