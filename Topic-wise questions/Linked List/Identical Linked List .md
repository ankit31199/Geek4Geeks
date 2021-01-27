# [Identical Linked List ](https://practice.geeksforgeeks.org/problems/identical-linked-lists/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)

<p>Given two Singly Linked List of N and M nodes respectively. The task is to check whether two linked lists are identical or not. 
Two Linked Lists are identical when they have same data and with same arrangement too..</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList1: 1->2->3->4->5->6  
LinkedList2: 99->59->42->20</span>
<strong>Output: </strong><span id="example-output-1"> Not identical
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList1: 1->2->3->4->5
LinkedList2: 1->2->3->4->5</span>
<strong>Output: </strong><span id="example-output-1"> identical
</pre>


</div>
</div>

```cpp
int count(struct Node *head)
{
    int c=0;
    while(head)
    {
        c++;
        head=head->next;
    }
    return c;
}
bool areIdentical(struct Node *head1, struct Node *head2)
{
    int N,M,i=0;
    N=count(head1);
    M=count(head2);
    if(N!=M)
    return false;
    else
    {
        while((head1)&&i<N)
        {
            if(head1->data!=head2->data)
            return false;
            
            head1=head1->next;
            head2=head2->next;
            i++;
        }
        return true;
    }
    
}
```
