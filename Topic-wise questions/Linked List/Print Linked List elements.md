# [Print Linked List elements ](https://practice.geeksforgeeks.org/problems/print-linked-list-elements/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)
<p>You are given the pointer to the head node of a linked list. You have to print all of its elements in order in a single line.

Input:
You have to complete a method which takes one argument: the head of the linked list. You should not read any input from stdin/console. The struct Node has a data part which stores the data and a next pointer which points to the next element of the linked list. There are multiple test cases. For each test case, this method will be called individually.

Output:
Print the elements of the linked list in a single line separated by a single space.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">Input:
N=2
LinkedList={1 , 2}</span>
<strong>Output: </strong><span id="example-output-1"> 1 2
</pre>


</div>

```cpp
void display(Node *head)
{
  if (head==NULL)
  return ;
  while(head)
  {
      cout<<head->data<<" ";
      head=head->next;
  }
}

