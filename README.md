# LinkedList
### Conver the array to linked list
```java
class Node{
    int data;
    Node next;
    Node(int data,Node next)
    {
        this.data = data;
        this.next = next;
    }
    Node(int data)
    {
        this.data = data;
        this.next = null;
    }
};
public class Main
{
    private static Node convert(int[] arr)
    {
        Node head = new Node(arr[0]);
        Node mover = head;
        for(int i=1;i<arr.length;i++)
        {
            Node temp = new Node(arr[i]);
            mover.next = temp;
            mover = temp;
        }
        return head;
    }
	public static void main(String[] args) 
	{
	    int[] arr = {12,5,6,8};
	    Node head = convert(arr);
	    System.out.print(head.data);
	}
}
```
### Traversal of array
```java
class Node{
    int data;
    Node next;
    Node(int data,Node next)
    {
        this.data = data;
        this.next = next;
    }
    Node(int data)
    {
        this.data = data;
        this.next = null;
    }
};
public class Main
{
    private static Node convert(int[] arr)
    {
        Node head = new Node(arr[0]);
        Node mover = head;
        for(int i=1;i<arr.length;i++)
        {
            Node temp = new Node(arr[i]);
            mover.next = temp;
            mover = temp;
        }
        return head;
    }
	public static void main(String[] args) 
	{
	    int[] arr = {12,5,6,8};
	    Node head = convert(arr);
	    Node temp = head;
	    while(temp!=null)
	    {
	        System.out.print(temp.data+" ");
	        temp = temp.next;
	    }
	}
}
```
### 1290. Convert Binary Number in a Linked List to Integer
[Leetcode link](https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/)
<br>
Given head which is a reference node to a singly-linked list. The value of each node in the linked list is either 0 or 1. The linked list holds the binary representation of a number.
Return the decimal value of the number in the linked list.
The most significant bit is at the head of the linked list.

Example 1:
<br>
![](https://assets.leetcode.com/uploads/2019/12/05/graph-1.png)
<br>
Input: head = [1,0,1]
Output: 5
Explanation: (101) in base 2 = (5) in base 10

Example 2:
Input: head = [0]
Output: 0

Constraints:
The Linked List is not empty.
Number of nodes will not exceed 30.
Each node's value is either 0 or 1.

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public int find_len(ListNode head)
    {
        ListNode temp = head;
        int c = 0;
        while(temp != null)
        {
            c++;
            temp = temp.next;
        }
        return c;
    }
    public int getDecimalValue(ListNode head) {
        int num = 0;
        int l = find_len(head)-1;
        ListNode temp = head;
        while(temp != null)
        {
            num += (temp.val)*Math.pow(2,l--);
            temp = temp.next;
        }
        return num;
    }
}
```
### 2. Add Two Numbers
[Leetcode link](https://leetcode.com/problems/add-two-numbers/description/)
<br>
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.
You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example 1:
<br>
![](https://assets.leetcode.com/uploads/2020/10/02/addtwonumber1.jpg)
<br>
Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.

Example 2:
Input: l1 = [0], l2 = [0]
Output: [0]

Example 3:
Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]

Constraints:
The number of nodes in each linked list is in the range [1, 100].
0 <= Node.val <= 9
It is guaranteed that the list represents a number that does not have leading zeros.
> [Reference](https://www.youtube.com/watch?v=XmRrGzR6udg)
### 328. Odd Even Linked List
[Leetcode link](https://leetcode.com/problems/odd-even-linked-list/)
<br>
Given the head of a singly linked list, group all the nodes with odd indices together followed by the nodes with even indices, and return the reordered list.
The first node is considered odd, and the second node is even, and so on.
Note that the relative order inside both the even and odd groups should remain as it was in the input.
You must solve the problem in O(1) extra space complexity and O(n) time complexity.

Example 1:
![](https://assets.leetcode.com/uploads/2021/03/10/oddeven-linked-list.jpg)
<br>
Input: head = [1,2,3,4,5]
Output: [1,3,5,2,4]

Example 2:
Input: head = [2,1,3,5,6,4,7]
Output: [2,3,6,7,1,5,4]

Constraints:
The number of nodes in the linked list is in the range [0, 104].
-106 <= Node.val <= 106

### 2095. Delete the Middle Node of a Linked List
[Leetcode link](https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/)
<br>
You are given the head of a linked list. Delete the middle node, and return the head of the modified linked list.
The middle node of a linked list of size n is the ⌊n / 2⌋th node from the start using 0-based indexing, where ⌊x⌋ denotes the largest integer less than or equal to x.
For n = 1, 2, 3, 4, and 5, the middle nodes are 0, 1, 1, 2, and 2, respectively.
 
Example 1:
Input: head = [1,3,4,7,1,2,6]
Output: [1,3,4,1,2,6]
Explanation:
The above figure represents the given linked list. The indices of the nodes are written below.
Since n = 7, node 3 with value 7 is the middle node, which is marked in red.
We return the new list after removing this node. 

Example 2:

Input: head = [1,2,3,4]
Output: [1,2,4]
Explanation:
The above figure represents the given linked list.
For n = 4, node 2 with value 3 is the middle node, which is marked in red.

Example 3:

Input: head = [2,1]
Output: [2]
Explanation:
The above figure represents the given linked list.
For n = 2, node 1 with value 1 is the middle node, which is marked in red.
Node 0 with value 2 is the only node remaining after removing node 1.

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public int find_len(ListNode head)
    {
        ListNode temp = head;
        int c = 0;
        while(temp != null)
        {
            c++;
            temp = temp.next;
        }
        return c;
    }
    public ListNode deleteMiddle(ListNode head) {
        int m = find_len(head)/2;
        if(m==0) return head.next;
        int c= 0;
        ListNode temp = head;
        while(c<m-1)
        {
            temp = temp.next;
            c++;
        }
        temp.next = temp.next.next;
        return head;
    }
}
```
### 3217. Delete Nodes From Linked List Present in Array
[Letcode link](https://leetcode.com/problems/delete-nodes-from-linked-list-present-in-array/submissions/1381318955?envType=daily-question&envId=2024-09-06)
<br>
You are given an array of integers nums and the head of a linked list. Return the head of the modified linked list after removing all nodes from the linked list that have a value that exists in nums.

Example 1:
Input: nums = [1,2,3], head = [1,2,3,4,5]
Output: [4,5]
Explanation:
Remove the nodes with values 1, 2, and 3.

Example 2:
Input: nums = [1], head = [1,2,1,2,1,2]
Output: [2,2,2]
Explanation:
Remove the nodes with value 1.

Example 3:
Input: nums = [5], head = [1,2,3,4]
Output: [1,2,3,4]

Constraints:
1 <= nums.length <= 105
1 <= nums[i] <= 105
All elements in nums are unique.
The number of nodes in the given list is in the range [1, 105].
1 <= Node.val <= 105
The input is generated such that there is at least one node in the linked list that has a value not present in nums.

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode modifiedList(int[] nums, ListNode head) {
        Set<Integer> set = Arrays.stream(nums)  
                                 .boxed()       
                                 .collect(Collectors.toSet());
        ListNode head1 = new ListNode();
        ListNode mover = new ListNode();
        while(head != null)
        {
            if(!set.contains(head.val)) 
            {
                if(head1.next == null)
                {
                    head1 = head;
                    mover = head1;
                }
                else
                {
                    mover.next = head;
                    mover = head;
                }
            }
            head = head.next;
        }
        mover.next = null;
        return head1;
    }
}
```
### 2326. Spiral Matrix IV
[Leetcode link](https://leetcode.com/problems/spiral-matrix-iv/description/?envType=daily-question&envId=2024-09-09)
<br>
You are given two integers m and n, which represent the dimensions of a matrix. You are also given the head of a linked list of integers.
Generate an m x n matrix that contains the integers in the linked list presented in spiral order (clockwise), starting from the top-left of the matrix. If there are remaining empty spaces, fill them with -1. Return the generated matrix.

Example 1:
![](https://assets.leetcode.com/uploads/2022/05/09/ex1new.jpg)
<br>
Input: m = 3, n = 5, head = [3,0,2,6,8,1,7,9,4,2,5,5,0]
Output: [[3,0,2,6,8],[5,0,-1,-1,1],[5,2,4,9,7]]
Explanation: The diagram above shows how the values are printed in the matrix.
Note that the remaining spaces in the matrix are filled with -1.

Example 2:
![](https://assets.leetcode.com/uploads/2022/05/11/ex2.jpg)
<br>
Input: m = 1, n = 4, head = [0,1,2]
Output: [[0,1,2,-1]]
Explanation: The diagram above shows how the values are printed from left to right in the matrix.
The last space in the matrix is set to -1.

Constraints:
1 <= m, n <= 105
1 <= m * n <= 105
The number of nodes in the list is in the range [1, m * n].
0 <= Node.val <= 1000

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * int val;
 * ListNode next;
 * ListNode() {}
 * ListNode(int val) { this.val = val; }
 * ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public int[][] spiralMatrix(int m, int n, ListNode head) 
    {
        int[][] ans = new int[m][n];
        int top = 0,left = 0,right = n-1,bottom = m-1;
        while(top<=bottom && left<=right)
        {
            for(int i=left;i<=right;i++) 
            {
                if(head == null) ans[top][i]=-1;
                else 
                {
                    System.out.println(head.val+" "+i+" "+top);
                    ans[top][i]=head.val;
                    head = head.next;
                }
            }
            top++;
            for(int i=top;i<=bottom;i++)
            {
                if(head == null) ans[i][right] = -1;
                else 
                {
                    ans[i][right] = head.val;
                    head = head.next;
                }
            }
            right--;
            if(top<=bottom)
            {
                for(int i=right;i>=left;i--)
                {
                    if(head == null) ans[bottom][i] = -1;
                    else 
                    {
                        ans[bottom][i]=head.val;
                        head = head.next;
                    }
                }
                bottom--;
            }
            if(left<=right)
            {
                for(int i=bottom;i>=top;i--)
                {
                    if(head == null) ans[i][left] = -1;
                    else 
                    {
                        ans[i][left]=head.val;
                        head = head.next;
                    }
                }
                left++;
            }
        }
        return ans;
    }
}
```
- In this code we spirally initialize the value from the linked list.
- We already see the spiral traversal of the matrix so give it to the same
- Each time we initiallize the head.val value to the current matrix position
- If the head reach null then we initiallize the current matrix position by -1.

### 2807. Insert Greatest Common Divisors in Linked List
[Leetcode link](https://leetcode.com/problems/insert-greatest-common-divisors-in-linked-list/description/?envType=daily-question&envId=2024-09-10)
<br>
Given the head of a linked list head, in which each node contains an integer value. Between every pair of adjacent nodes, insert a new node with a value equal to the greatest common divisor of them. Return the linked list after insertion. The greatest common divisor of two numbers is the largest positive integer that evenly divides both numbers.

Example 1:
<br>
![](https://assets.leetcode.com/uploads/2023/07/18/ex1_copy.png)
<br>
Input: head = [18,6,10,3]
Output: [18,6,6,2,10,1,3]
Explanation: The 1st diagram denotes the initial linked list and the 2nd diagram denotes the linked list after inserting the new nodes (nodes in blue are the inserted nodes).
- We insert the greatest common divisor of 18 and 6 = 6 between the 1st and the 2nd nodes.
- We insert the greatest common divisor of 6 and 10 = 2 between the 2nd and the 3rd nodes.
- We insert the greatest common divisor of 10 and 3 = 1 between the 3rd and the 4th nodes.
There are no more adjacent nodes, so we return the linked list.
Example 2:
<br>
![](https://assets.leetcode.com/uploads/2023/07/18/ex2_copy1.png)
<br>
Input: head = [7]
Output: [7]
Explanation: The 1st diagram denotes the initial linked list and the 2nd diagram denotes the linked list after inserting the new nodes.
There are no pairs of adjacent nodes, so we return the initial linked list.

Constraints:
The number of nodes in the list is in the range [1, 5000].
1 <= Node.val <= 1000

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode insertGreatestCommonDivisors(ListNode head) {
        ListNode temp = head;
        while(temp.next != null)
        {
            ListNode newnode = new ListNode(find(temp.val,temp.next.val));
            newnode.next = temp.next;
            temp.next = newnode;
            temp = newnode;
            temp = temp.next;
        }
        return head;
    }
    public int find(int a,int b)
    {
        int min = Math.min(a,b);
        for(int i = min;i>=1;i--)
        {
            if(a%i==0 && b%i==0) return i;
        }
        return 1;
    }
}
```
- In this code we given a head of the linked list.
- we travel throught the last's before element so in the while loop condition we put it as temp.next != null
- then we get the current value and the current values next value and find gcd of that two number
- then we insert the number after the current position so the the newnode next will be the temps next and the temps next will be new node finally we assign the temp by newnode.
- then we travel the temp by temp.next.
- and finally we return the head of the linked list.
