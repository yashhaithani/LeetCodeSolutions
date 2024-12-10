class Solution {
    public int maximumLength(String s) {
        int[] f1=new int[26];
        int[] f2=new int[26];
        int curr=1;
        int ans=-1;
        char[] a=s.toCharArray();
        f2[(int)(a[0]-'a')]=1;
        f1[(int)(a[0]-'a')]=1;
        int n=s.length();
        for(int i=1;i<n;i++){
            if(a[i]==a[i-1]){
                curr++;
            }else{
                curr=1;
            }
            int g=(int)(a[i]-'a');
            if(curr>f1[g]){
                f1[g]=curr;
                ans=Math.max(ans,curr-2);
                if(f2[g]>=2)ans=Math.max(curr-1,ans);
                f2[g]=1;
            }
            else if(curr==f1[g]-1){
                ans=Math.max(curr,ans);
                ans=Math.max(ans,curr-2);
            }else if(curr==f1[g]){
                f2[g]++;
                if(f2[g]>=3)ans=Math.max(curr,ans);
            }
        }
        return ans<=0?-1:ans;
    }
}
