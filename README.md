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
 
