#### LCP
###### Medium Accuracy:
52.37%
###### Submissions: 
6403 Points: 4

Lamp Geeks Summer Carnival is LIVE NOW  
Note: This POTD is a part of Geek Summer Carnival. Solve all POTD consecutively from 5th to 10th April and get a chance to win exclusive discount vouchers on our GfG courses.

Geek is at the geek summer carnival. He is given an array of N strings. To unlock exclusive course discounts he needs to find the longest common prefix among all strings present in the array. Can you help him ?


###### Example 1:

###### Input:
N = 4
ar[] = {geeksforgeeks, geeks, geek, geezer}

###### Output:
gee

###### Explanation: 
Longest common prefix in all the given string is gee. 
 

###### Example 2:

###### Input:
N = 3
ar[] = {apple, ape, april}

###### Output:
ap

###### Your Task:
You don't need to read input or print anything. Complete the function LCP() that takes integer n and ar[] as input parameters and return the LCP (in case there is no common prefix return -1). 

 

Expected time complexity: O(NlogN)
Expected space complexity: O(string length)


###### Constraints:
1 <= N <= 10^3
1 <= String Length <= 100

```java
class Solution
{
    public String lcp(String s[],int n)
    {
        // Write your code here
        String str = "";
        Arrays.sort(s);
        for(int i = 0;i<s[0].length();i++){
            if(s[0].charAt(i) == s[n-1].charAt(i)){
                str = str+s[0].charAt(i);
            }
            else
            break;
        }
        if(str.length()==0)
        return "-1";
        else
        return str;
    }
}
```

