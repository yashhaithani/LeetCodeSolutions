class Solution {
    private int dia;

    public int minimumDiameterAfterMerge(int[][] edges1, int[][] edges2) {
        int n = edges1.length + 1, m = edges2.length + 1;
        List<Integer>[] t1 = new List[n], t2 = new List[m];
        Arrays.setAll(t1, i -> new ArrayList<>());
        Arrays.setAll(t2, i -> new ArrayList<>());
        for (int[] e : edges1) {
            int u = e[0], v = e[1];
            t1[u].add(v);
            t1[v].add(u);
        }
        for (int[] e : edges2) {
            int u = e[0], v = e[1];
            t2[u].add(v);
            t2[v].add(u);
        }
        dia = 0;
        diameterOf(t1, 0, -1);
        int dia1 = dia;
        dia = 0;
        diameterOf(t2, 0, -1);
        int dia2 = dia;
        return Math.max(Math.max(dia1, dia2), (dia1 + 1) / 2 + 1 + (dia2 + 1) / 2);
    }

    private int diameterOf(List<Integer>[] tree, int i, int pa) {
        int max1 = 0, max2 = 0;
        for (int j : tree[i]) {
            if (j == pa) continue;
            int d = diameterOf(tree, j, i);
            if (max1 <= d) {
                max2 = max1;
                max1 = d;
            } else if (max2 < d) {
                max2 = d;
            }
        }
        dia = Math.max(dia, max1 + max2);
        return max1 + 1;
    }

}
