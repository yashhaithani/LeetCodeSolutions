class Solution {
    private int idx = 0;

    public boolean parseBoolExpr(final String expression) {
        this.idx = 0;

        if(expression.length() == 1)
            return expression.charAt(0) == 't';
        
        return this.helper(expression);
    }

    private boolean helper(final String s) {
        final char operator = s.charAt(this.idx);

        this.idx += 2;
        
        char c = s.charAt(this.idx);

        boolean result = false;

        if(c == 't') {
            result = true;
            this.idx++;
        } else if(c == 'f') {
            result = false;
            this.idx++;
        } else {
            result = this.helper(s);
        }

        c = s.charAt(this.idx);

        while(c != ')') {
            if(c == ',') {
                c = s.charAt(++this.idx);
                continue;
            }

            boolean curr = false;

            if(c == 't') {
                curr = true;
                this.idx++;
            } else if(c == 'f') {
                curr = false;
                this.idx++;
            } else {
                curr = helper(s);
            }

            if(operator == '&')
                result &= curr;
            else if(operator == '|')
                result |= curr;

            c = s.charAt(this.idx);
        }

        this.idx++;

        return operator == '!' ? !result : result;
    }
}
