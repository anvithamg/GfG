## Sum of nodes within k distance from target 
 **Medium Accuracy**: 68.17% **Submissions:** 2249 Points: 4
Lamp Geeks Summer Carnival is LIVE NOW   
**Note:** This POTD is a part of Geek Summer Carnival. Solve all POTD consecutively from 5th to 10th April and get a chance to win exclusive discount vouchers on our GfG courses.

Geek is at the geek summer carnival. To unlock discounts on exclusive courses he is given a card with a binary tree, a target node and a positive integer k on it. 
He needs to find the sum of all nodes within a max distance k from target node such that the target node is included in sum.

###### Example 1:

###### Input:
target = 9 
k = 1
Binary Tree = 
            1
           /  \
          2    9
        /     /  \
       4     5    7
      /  \       /  \
     8    19    20   11
    /   /   \
  30   40   50

###### Output: 22

###### Explanation: 
Nodes within distance 1 from 9 
9 + 5 + 7 + 1 = 22

###### Example 2:

###### Input:
target = 40 
k = 2
Binary Tree = 
            1
           /  \
          2    9
        /     /  \
       4     5    7
      /  \       /  \
     8    19    20   11
    /   /   \
  30   40   50

###### Output: 113

###### Explanation:
Nodes within distance 2 from 40,
40 + 19 + 50 + 4 = 113
Your Task:
You don't need to read input or print anything. Complete the function sum_at_distK() that takes the root of the given binary tree, target and k as input parameters and return the required sum. 

Expected time complexity: O(n)
Expected space complexity: O(n)

###### Constraints:
1 <= number of nodes <= 1000
1 <= data in nodes,target <= 10000
1 <= k <= 20
```java
class solver{
    static int sum = 0;
    static int sum_at_distK(Node root, int target, int k){
        // code here
        sum = 0;
        find(root,target,k);
        return sum;
    }
    static int find(Node root,int target,int k){
        if(root == null)
            return -1;
        if(root.data == target){
            sum(root,k);
            return k-1;
        }
        int left = find(root.left,target,k);
        if(left!= -1){
            sum += root.data;
            sum(root.right,left-1);
            return left -1;
        }
        int right = find(root.right,target,k);
        if(right != -1){
            sum+= root.data;
            sum(root.left,right-1);
            return right -1;
        }
        return -1;
            
    }
    static void sum(Node root,int k){
        if(k<0||root==null)
            return;
        sum+=root.data;
        sum(root.left,k-1);
        sum(root.right,k-1);
    }
}
```
