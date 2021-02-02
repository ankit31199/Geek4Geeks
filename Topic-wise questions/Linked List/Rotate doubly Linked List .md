# [Rotate doubly Linked List  ](https://practice.geeksforgeeks.org/problems/rotate-doubly-linked-list-by-p-nodes/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given a doubly linked list, rotate the linked list counter-clockwise by P nodes. Here P is a given positive integer and is smaller than the count of nodes(N) in a linked list.

Input:
The first line of input contains an integer T denoting the no of test cases. For each test case, the first line of input contains two integers N and P denoting the number of nodes in Linked List and the number of nodes to be rotated respectively.

Output:
For each test case, output the final linked list after the P rotations in it.

Constraints:
1 <= T <= 100
2 <= N <= 100
1 <= P <= N</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">1
6 2
1 2 3 4 5 6</span>
<strong>Output: </strong><span id="example-output-1">3 4 5 6 1 2
</pre>


</div>

```cpp
struct node*update(struct node*start,int p)
{
    struct node*ptr1=start,*ptr2=start,*ptr3;
        int k=0;
        while(ptr1!=NULL)
        {
            if(k==p)
                break;
            k++;
            ptr1=ptr1->next;
        }
        ptr3=ptr1->prev; 
        while(ptr2->next!=NULL)
        ptr2=ptr2->next;
        ptr2->next=start;
        ptr3->next=NULL;
        start->prev=ptr2;
        start=ptr1;
        return start;
}
