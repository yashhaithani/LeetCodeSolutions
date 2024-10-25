class Trie{
    class Node{
        boolean eow;
        Node[]children;
        Node(){
            children=new Node[27];
        }
    }
    Node root;
    Trie(){
        root=new Node();
    }
    public void insert(String s){
        Node curr=root;
        for(char ch:s.toCharArray()){
            int idx=ch-'a';
            if(ch=='/')idx=26;
            if(curr.children[idx]==null)curr.children[idx]=new Node();
            curr=curr.children[idx];
        }
        curr=curr.children[26]=new Node();
        curr.eow=true;
    }
    public boolean search(String s){
        Node curr=root;
        for(char ch:s.toCharArray()){
            int idx=ch-'a';
            if(ch=='/')idx=26;
            if(curr.children[idx]==null)return false;
            curr=curr.children[idx];
            if(curr.eow==true)return true;
        }
        return false;
    }
}
class Solution {
    public List<String> removeSubfolders(String[] folder) {
        Trie trie=new Trie();
        Arrays.sort(folder,(a,b)->a.length()-b.length());
        List<String>ans=new ArrayList<>();
        for(String s:folder){
            if(!trie.search(s)){
                ans.add(s);
                trie.insert(s);
            }
        }
        return ans;
    }
}
