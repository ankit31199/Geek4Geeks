# [Add 1 to a number represented as linked list  ](https://practice.geeksforgeeks.org/problems/add-1-to-a-number-represented-as-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>A number N is represented in Linked List such that each digit corresponds to a node in linked list. You need to add 1 to it.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 4->5->6</span>
<strong>Output: </strong><span id="example-output-1"> 457
-10 -2  0  3
</pre>


</div>
<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 1->2->3</span>
<strong>Output: </strong><span id="example-output-1"> 124
-10 -2  0  3
</pre>


</div>

```cpp
Node* reverse(Node *head) 
// this function reverses the linked list
{
    Node * prev = NULL;
    Node * current = head;
    Node * next;
    
    while (current != NULL) 
    { 
        next = current->next;     // storing next node
        current->next = prev;     // linking current node to previous
        prev = current;           // updating prev
        current = next;           // updating current
    }
    
    return prev; 
} 

Node* addOne(Node *head) 
{ 
    head = reverse(head);           // reversing list to make addition easy
    
    Node* current = head;
    int carry = 1;
    
    while(carry)
    {
        current->data += 1;         // adding one to current node
        
        if(current->data < 10) return reverse(head);
            // if no carry we can reverse back list and return it
        else current->data = 0;
            // else we continue with taking carry forward
        
        if(current->next == NULL) break;
            // if, end of list, we break from loop
        else current = current->next;
            // else we move to next node
    }
    
    current->next = new Node(1);  // adding new node for the carried 1
    return reverse(head);
}
