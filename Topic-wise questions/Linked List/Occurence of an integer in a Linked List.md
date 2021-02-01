# [Occurence of an integer in a Linked List ](https://practice.geeksforgeeks.org/problems/occurence-of-an-integer-in-a-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given a singly linked list and a key, count the number of occurrences of given key in the linked list.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">N = 7
Link List = 1->2->1->2->1->3->1
search_for = 1</span>
<strong>Output: </strong><span id="example-output-1"> 4
</pre>


</div>

```cpp
int count(struct node* head, int search_for)
{
    node *temp;
    temp=head;
    int c=0;
while(temp)
{
    if(search_for == (temp->data))
    c++;
    temp=temp->next;
}
return c;
}
