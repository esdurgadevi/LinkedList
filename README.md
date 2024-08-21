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
![](https://assets.leetcode.com/uploads/2019/12/05/graph-1.png)
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

