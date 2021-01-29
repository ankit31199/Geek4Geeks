# [Node at a given index in linked list ](https://practice.geeksforgeeks.org/problems/node-at-a-given-index-in-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-1page1category[]Linked%20List)
<p>Given a singly linked list with N nodes and a number X. The task is to find the node at the given index (X)(1 based index) of linked list. 

Input:
First line of input contains number of testcases T. For each testcase, first line of input contains space seperated two integers, length of linked list and X.

Output:
For each testcase, there will be single line of output containing data at Xth node.

User Task:
The task is to complete the function GetNth() which takes head reference and index as arguments and should return the data at Xth position in the linked list.</p>


<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">2
6 5
1 2 3 4 657 76
10 2
8 7 10 8 6 1 20 91 21 2</span>
<strong>Output: </strong><span id="example-output-1">657
7
</pre>


</div>
</div>

```cpp
int GetNth(struct node* head, int index){
    int i=0;
    node* temp;
    temp=head;
    while(temp!=NULL)
    {
        if(i+1==index)
        {
            return (temp->data);

        }
        temp=temp->next;
        i++;
    }
}


