# [Check If Circular Linked List ](https://practice.geeksforgeeks.org/problems/circular-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)
<p>Given two Singly Linked List of N and M nodes respectively. The task is to check whether two linked lists are identical or not. 
Two Linked Lists are identical when they have same data and with same arrangement too..</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 1->2->3->4->5
(the first and last node is connected,
i.e. 5 --> 1)</span>
<strong>Output: </strong><span id="example-output- 1"> 1
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 2->4->6->7->5->1</span>
<strong>Output: </strong><span id="example-output-1"> 0
</pre>


</div>
</div>

```cpp
bool isCircular(struct Node *head)
{
    if(!head)
        return true;
    
    Node *temp=head;
    
    while(head&&head->next!=temp)
        head=head->next;
    
    if(!head||!(head->next))
        return false;
    
    return true;
}

