#  Longest Consecutive Sequence

https://leetcode.cn/problems/longest-consecutive-sequence/

```java
class Solution {
    public int longestConsecutive(int[] nums) {
        Set<Integer> set = new HashSet<>();//去重复
        for(int i:nums) set.add(i);
      
        int max=0;//之所以要声明一个新的变量是为了重新判定
        for(int n:set){
            if(!set.contains(n-1)){//不包含cur的下一个证明目前的cur是起点
                int cur=n;
                int count=1;
                
                while(set.contains(cur+1)){
                    cur++;
                    count++;
                }   
                max=Math.max(max,count);
            }
        }
        return max;
    }
}
