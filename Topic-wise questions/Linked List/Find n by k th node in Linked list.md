# [Find n/k th node in Linked list ](https://practice.geeksforgeeks.org/problems/circular-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)
<p>Given a singly linked list and a number k. Write a function to find the (N/k)th element, where N is the number of elements in the list. We need to consider ceil value in case of decimals.

Input:
The first line of input contains an integer T denoting the number of test cases. The first line of each test case consists of an integer N. The second line consists of N spaced integers.The last line consists of an integer k.

Output:
Print the data value of (N/k)th node in the Linked List.

User Task:
The task is to complete the function fractional_node() which should find the n/kth node in the linked list and return its data value.

Constraints: 
1 <= T <= 100
1 <= N <= 100</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">2
6
1 2 3 4 5 6
2
5
2 7 9 3 5
3</span>
<strong>Output: </strong><span id="example-output-1">3
7
</pre>


</div>

```cpp
int fractional_node(struct Node *head, int k)
{
    // your code here
     // Corner cases 
    if (k <= 0 || head == NULL) 
        return NULL; 
  
    Node* fractionalNode = NULL; 
      
    // Traverse the given list  
    int i = 0; 
    for (Node* temp = head; temp != NULL; temp = temp->next) { 
  
        // For every k nodes, we move fractionalNode one 
        // step ahead.  
        if (i % k == 0) { 
  
            // First time we see a multiple of k 
            if (fractionalNode == NULL) 
                fractionalNode = head; 
  
            else
                fractionalNode = fractionalNode->next; 
        } 
        i++; 
    } 
    return fractionalNode->data; 
} 
 
