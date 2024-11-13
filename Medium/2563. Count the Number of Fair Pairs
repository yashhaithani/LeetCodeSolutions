class Solution {
    public long countFairPairs(int[] nums, int lower, int upper) {
        Arrays.sort(nums); 
        long pairsWithUpper = findLessThanEqualTo(nums, upper);
        long pairsWithLowerMinus1 = findLessThanEqualTo(nums, lower - 1);
        return pairsWithUpper - pairsWithLowerMinus1;
    }

    private long findLessThanEqualTo(int[] nums, int targetSum) {
        int n = nums.length;
        long pairs = 0;
        int left = 0;
        int right = n - 1;


        while (left < right) {
            if (nums[left] + nums[right] <= targetSum) {
                pairs += (right - left);
                left++; 
            } else {
                right--; 
            }
        }

        return pairs;
    }
}
