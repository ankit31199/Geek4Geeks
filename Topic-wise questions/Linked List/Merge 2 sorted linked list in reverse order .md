# [Merge 2 sorted linked list in reverse order  ](https://practice.geeksforgeeks.org/problems/merge-2-sorted-linked-list-in-reverse-order/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given two linked lists of size N and M, which are sorted in non-decreasing order. The task is to merge them in such a way that the resulting list is in decreasing order.

Input:
First line of input contains number of testcases T. For each testcase, first line of input conatains length of both linked lists N and M respectively. Next two lines contains N and M elements of two linked lists.

Output:
For each testcase, print the merged linked list which is in non-increasing order.

User Task:
The task is to complete the function mergeResult() which takes reference to the heads of both linked list and returns the pointer to the merged linked list.

Constraints:
1 <=T<= 50
1 <= N, M <= 1000</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">
2
4 3
5 10 15 40 
2 3 20
2 2
1 1
2 4</span>
<strong>Output: </strong><span id="example-output-1"> 
40 20 15 10 5 3 2 4 2 1 1 
</pre>


</div>

```cpp
struct Node * mergeResult(Node *a,Node *b)

{ 
    // If both lists are empty 
    if (a==NULL && b==NULL) return NULL; 
  
    // Initialize head of resultant list 
    Node *res = NULL; 
  
    // Traverse both lists while both of then 
    // have nodes. 
    while (a != NULL && b != NULL) 
    { 
        // If a's current value is smaller or equal to 
        // b's current value. 
        if (a->data <= b->data) 
        { 
            // Store next of current Node in first list 
            Node *temp = a->next; 
  
            // Add 'a' at the front of resultant list 
            a->next = res; 
            res = a; 
  
            // Move ahead in first list 
            a = temp; 
        } 
  
        // If a's value is greater. Below steps are similar 
        // to above (Only 'a' is replaced with 'b') 
        else
        { 
            Node *temp = b->next; 
            b->next = res; 
            res = b; 
            b = temp; 
        } 
    } 
  
    // If second list reached end, but first list has 
    // nodes. Add remaining nodes of first list at the 
    // front of result list 
    while (a != NULL) 
    { 
        Node *temp = a->next; 
        a->next = res; 
        res = a; 
        a = temp; 
    } 
  
    // If first list reached end, but second list has 
    // node. Add remaining nodes of first list at the 
    // front of result list 
    while (b != NULL) 
    { 
        Node *temp = b->next; 
        b->next = res; 
        res = b; 
        b = temp; 
    } 
  
    return res; 
} 
