class Solution {
    public int[] smallestRange(List<List<Integer>> nums) {
        if (nums.size() == 1) {
            return new int[] { nums.get(0).get(0), nums.get(0).get(0) };
        }
        int k = nums.size();
        int minK = nums.get(0).get(0), minArr = 0;
        int maxK = nums.get(0).get(0), maxArr = 0;
        for (int i = 1; i < k; ++i) {
            List<Integer> list = nums.get(i);
            int val = list.get(0);
            if (val > maxK) {
                maxK = val;
                maxArr = i;
            }
            if (val < minK) {
                minK = val;
                minArr = i;
            }
        }
        int[] ret = new int[] { minK, maxK };
        int[] pos = new int[k];
        boolean done = false;
        int curListLen;
        while (!done) {
            List<Integer> curMinList = nums.get(minArr);
            pos[minArr]++;
            if (curMinList.size() == pos[minArr]) {
                done = true;
                continue;
            }
            int next = curMinList.get(pos[minArr]);
            minK = next;
            for (int i = 0; i < k; ++i) {
                curMinList = nums.get(i);
                curListLen = curMinList.size();
                for (int curIdx = pos[i]; curIdx < curListLen && curMinList.get(curIdx) <= next; curIdx++) {
                    pos[i] = curIdx;
                }
                int curVal = curMinList.get(pos[i]);
                if (curVal < minK) {
                    minK = curVal;
                    minArr = i;
                }
                if (curVal > maxK) {
                    maxK = curVal;
                    maxArr = i;
                }
            }
            if (maxK - minK < ret[1] - ret[0]) {
                ret[1] = maxK;
                ret[0] = minK;
            }
        }
        return ret;
    }
}
