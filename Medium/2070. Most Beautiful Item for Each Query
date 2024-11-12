class Solution {
    public int[] maximumBeauty(int[][] items, int[] queries) {
        Arrays.sort(items, (a, b) -> a[0] == b[0] ? b[1] - a[1] : a[0] - b[0]);
        int currMaxBeauty = 0;
        TreeMap<Integer, Integer> m = new TreeMap<>();
        for (int[] item : items) {
            if (item[1] <= currMaxBeauty) {
                continue;
            }
            currMaxBeauty = item[1];
            m.put(item[0], currMaxBeauty);
        }
        int[] res = new int[queries.length];
        for (int i = 0; i < queries.length; i++) {
            Map.Entry<Integer, Integer> entry = m.floorEntry(queries[i]);
            if (entry != null) {
                res[i] = entry.getValue();   
            }
        }
        return res;
    }
}
