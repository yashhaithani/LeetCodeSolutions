class Solution {
    private static final int MOD = (int) 1e9 + 7;

    public int countGoodStrings(int low, int high, int zero, int one) {
        if (zero > one) {
            return countGoodStrings(low, high, one, zero);
        }
        int[] dp = new int[high + 1];
        dp[0] = 1;
        int ans = 0;
        for (int i = 1; i <= high; i++) {
            if (i >= one) {
                dp[i] = (dp[i - zero] + dp[i - one]) % MOD;
            } else if (i >= zero) {
                dp[i] = dp[i - zero] % MOD;
            }
            if (i >= low) {
                ans = (ans + dp[i]) % MOD;
            }
        }
        return ans;
    }
}
