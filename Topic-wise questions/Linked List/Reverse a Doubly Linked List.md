# [Reverse a Doubly Linked List ](https://practice.geeksforgeeks.org/problems/reverse-a-doubly-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given a doubly linked list of n elements. The task is to reverse the doubly linked list.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 3 <--> 4 <--> 5</span>
<strong>Output: </strong><span id="example-output-1"> 5 4 3
-10 -2  0  3
</pre>


</div>
<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 75 <--> 122 <--> 59 <--> 196</span>
<strong>Output: </strong><span id="example-output-1"> 196 59 122 75
-10 -2  0  3
</pre>


</div>

```cpp
Node* reverseDLL(Node * head)
{
    

 Node *p,*temp;
 p=head;
 
 while(p)
 {
      if((p->next == NULL)&&(p!=NULL))
     head=p;
     temp=p->next;
     p->next=p->prev;
     p->prev=temp;
     p=p->prev;
     
    
     
 }
 return head;
    //Your code here
}
