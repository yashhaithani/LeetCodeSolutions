class Solution {
    public int maxCount(int[] banned, int n, int maxSum) {
        int sum = 0;
        int result = 0;
        boolean[] isBanned = new boolean[10001];
        for (int ban : banned) {
            isBanned[ban] = true;
        }
        for (int i = 1; i <= n; i++) {
            if (sum + i > maxSum) {
                break;
            }
            if (!isBanned[i]) {
                sum += i;
                result++;
            }
        }
        return result;
    }
}
