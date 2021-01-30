# [Linked List Insertion ](https://practice.geeksforgeeks.org/problems/linked-list-insertion-1587115620/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-1page1category[]Linked%20List)
<p>Create a link list of size N according to the given input literals. Each integer input is accompanied by an indicator which can either be 0 or 1. If it is 0, insert the integer in the beginning of the link list. If it is 1, insert the integer at the end of the link list. 
Hint: When inserting at the end, make sure that you handle NULL explicitly.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 9->0->5->1->6->1->2->0->5->0
</span>
<strong>Output: </strong><span id="example-output-1">  5 2 9 5 6
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList: 5->1->6->1->9->1</span>
<strong>Output: </strong><span id="example-output-1"> 5 6 9
</pre>


</div>
</div>

```cpp
Node *insertAtBegining(Node *head, int newData) {
    Node *temp = new Node(newData);
    if(head ==NULL)
    {
        return temp;
    }
    temp->next = head;
    return temp;
}


// function appends the data at the end of the list
Node *insertAtEnd(Node *head, int newData)  {
    Node *temp = new Node(newData);
    if(head == NULL){
       return temp;
    }
    else{
        Node *ptr = head;
        while(ptr->next!=NULL)
            ptr = ptr->next;
        ptr->next = temp;
        temp->next = NULL;
    }
   return head;
}
