#### Anagram of String
Basic Accuracy: 49.25% Submissions: 35935 Points: 1

Given two strings S1 and S2 in lowercase, the task is to make them anagram. The only allowed operation is to remove a character from any string. Find the minimum number of characters to be deleted to make both the strings anagram. Two strings are called anagram of each other if one of them can be converted into another by rearranging its letters.

Example 1:

Input:
S1 = bcadeh
S2 = hea
Output: 3
Explanation: We need to remove b, c
and d from S1.

Example 2:

Input:
S1 = cddgk
S2 = gcd
Output: 2
Explanation: We need to remove d and
k from S1.

Your Task:
Complete the function remAnagram() which takes two strings S1, S2 as input parameter, and returns minimum characters needs to be deleted.

Expected Time Complexity: O(max(|S1|, |S2|)), where |S| = length of string S.
Expected Auxiliary Space: O(26)

Constraints:
1 <= |S1|, |S2| <= 105

```java
    public int remAnagrams(String s,String s1){
        int minDel =0;
        HashMap<Character,Integer> m = new HashMap<>();
        for(int i=0;i<s.length();i++){
            m.put(s.charAt(i), m.getOrDefault(s.charAt(i), 0) + 1);
        }
        for(int i=0;i<s1.length();i++){
            m.put(s1.charAt(i), m.getOrDefault(s1.charAt(i), 0) -1);
        }
        for (HashMap.Entry<Character,Integer> entry : m.entrySet())  
            minDel += Math.abs(entry.getValue());
        return minDel;
    }
```
