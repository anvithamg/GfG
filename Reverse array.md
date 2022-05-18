####  Reverse an Array 
Given an array A of size N, print the reverse of it.

Input:
First line contains an integer denoting the test cases 'T'. T testcases follow. Each testcase contains two lines of input. First line contains N the size of the array A. The second line contains the elements of the array.

Output:
For each testcase, in a new line, print the array in reverse order.

Constraints:
1 <= T <= 100
1 <= N <=100
0 <= Ai <= 100

Example:
Input:
1
4
1 2 3 4
Output:
4 3 2 1
```java
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		//code
		Scanner obj = new Scanner(System.in);
		int t = obj.nextInt();
		for(int i=0;i<t;i++){
		    int n = obj.nextInt();
		    int[] arr = new int[n];
		    for(int j=0;j<n;j++){
		        arr[j] = obj.nextInt();
		    }
		    reverse(arr,n);
		}
	}
	public static void reverse(int[] arr, int n){
	    int[] rev = new int[n];
	    int j = 0;
	    for(int k=n-1;k>=0;k--){
	        rev[j++] = arr[k];
	    }
	    for(int k=0;k<n;k++){
	        System.out.print(rev[k]+" ");
	    }
	    System.out.println();
	}
}
```
