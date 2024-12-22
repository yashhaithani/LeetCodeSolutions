class Solution {
    public int[] leftmostBuildingQueries(int[] heights, int[][] queries) {
        List<int[]>[] lists = new ArrayList[heights.length];
        int[] res = new int[queries.length];
        Arrays.fill(res, -1);
        for (int i = 0; i < queries.length; i++) {
            if (queries[i][0] > queries[i][1]) {
                if (heights[queries[i][0]] > heights[queries[i][1]]) {
                    res[i] = queries[i][0];
                } else {
                    if (lists[queries[i][0]] == null)
                        lists[queries[i][0]] = new ArrayList<>();
                    lists[queries[i][0]].add(new int[] { heights[queries[i][1]], i });
                }
            } else if (queries[i][0] < queries[i][1]) {
                if (heights[queries[i][0]] < heights[queries[i][1]]) {
                    res[i] = queries[i][1];
                } else {
                    if (lists[queries[i][1]] == null)
                        lists[queries[i][1]] = new ArrayList<>();
                    lists[queries[i][1]].add(new int[] { heights[queries[i][0]], i });
                }
            } else {
                res[i] = queries[i][0];
            }
        }
        PriorityQueue<int[]> PQ = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        for (int i = 0; i < heights.length; i++) {
            while (!PQ.isEmpty() && PQ.peek()[0] < heights[i]) {
                res[PQ.poll()[1]] = i;
            }
            if (lists[i] != null) {
                for (int[] arr : lists[i]) {
                    PQ.add(arr);
                }
            }
        }
        return res;
    }
}
