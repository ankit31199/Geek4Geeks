# [Delete node in Doubly Linked List ](https://practice.geeksforgeeks.org/problems/delete-node-in-doubly-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)
<p>Given a doubly linked list and a position. The task is to delete a node from given position in a doubly linked list..</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList = 1 <--> 3 <--> 4 
x = 3</span>
<strong>Output: </strong><span id="example-output-1"> 1 3 
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList = 1 <--> 5 <--> 2 <--> 9  
x = 1</span>
<strong>Output: </strong><span id="example-output-1"> 5 2 9
</pre>


</div>
</div>

```cpp
Node* deleteNode(struct Node **head_ref,int x)
{

   struct Node *del = *head_ref;
   x = x-1;
   
   while(x--)
    del = del->next;


  if(*head_ref == NULL || del == NULL)
    return NULL;
 
  
  if(*head_ref == del)
    *head_ref = del->next;
 

  if(del->next != NULL)
    del->next->prev = del->prev;
 

  if(del->prev != NULL)
    del->prev->next = del->next;     
 
 
  free(del);
  return *head_ref;
}

```
