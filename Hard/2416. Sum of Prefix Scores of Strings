class Solution {
    public int[] sumPrefixScores(String[] words) {
        int wordCount = words.length;
        Integer[] sortedIndices = new Integer[wordCount];
        for (int i = 0; i < wordCount; i++) {
            sortedIndices[i] = i;
        }
        Arrays.sort(sortedIndices, (a, b) -> words[a].compareTo(words[b]));
        
        int[] commonPrefixLengths = calculateCommonPrefixLengths(words, sortedIndices);
        int[] scores = calculateScores(words, sortedIndices, commonPrefixLengths);
        return scores;
    }

    private int[] calculateCommonPrefixLengths(String[] words, Integer[] sortedIndices) {
        int[] commonPrefixLengths = new int[words.length];
        for (int i = 1; i < words.length; i++) {
            String prevWord = words[sortedIndices[i - 1]];
            String currWord = words[sortedIndices[i]];
            int commonLength = 0;
            while (commonLength < prevWord.length() && 
                   commonLength < currWord.length() && 
                   prevWord.charAt(commonLength) == currWord.charAt(commonLength)) {
                commonLength++;
            }
            commonPrefixLengths[i] = commonLength;
        }
        return commonPrefixLengths;
    }

    private int[] calculateScores(String[] words, Integer[] sortedIndices, int[] commonPrefixLengths) {
        int[] scores = new int[words.length];
        for (int i = 0; i < sortedIndices.length; i++) {
            int wordIndex = sortedIndices[i];
            int wordLength = words[wordIndex].length();
            scores[wordIndex] += wordLength;
            int j = i + 1;
            int commonLength = wordLength;
            while (j < words.length) {
                commonLength = Math.min(commonLength, commonPrefixLengths[j]);
                if (commonLength == 0) {
                    break;
                }
                scores[wordIndex] += commonLength;
                scores[sortedIndices[j]] += commonLength;
                j++;
            }
        }
        return scores;
    }
}
//Kds Appraoch 1
