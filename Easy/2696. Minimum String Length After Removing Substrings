class Solution {
    public int minLength(String s) {
        char[] stack = new char[s.length()+1];
        int last = -1;
        for (char c : s.toCharArray()) {
            if (last > -1 && (c == 'B' && stack[last] == 'A' || 
                                     c == 'D' && stack[last] == 'C')) 
            {
                last--;
            } else {
                last++;
                stack[last] = c;
            }
        }
        return last+1;
    }
}
