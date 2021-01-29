# [Modular Node ](https://practice.geeksforgeeks.org/problems/modular-node/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)
<p>Given a singly linked list and a number K, you are required to complete the function modularNode() which returns the modular node of the linked list.
A modular node is the last node of the linked list whose Index is divisible by the number K, i.e. i%k==0.

Input:
First line of input contains number of testcases T. For each testcase, first line of input contains length of Linked list N. Next line contains elements of the linked list and last line contains K.

Output:
For each test case the function must return the modular Node data, if no such node is possible then return "-1".</p>
<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">2
7
1 2 3 4 5 6 7
3
5
19 28 37 46 55
2</span>
<strong>Output: </strong><span id="example-output-1"> 6
46
</pre>

</div>

```cpp
int modularNode(Node* head, int k)
{
	int data=-1;
	if(head==NULL)
	return -1; int i=1;
	Node* temp=head;
	while(temp)
	{
	    if((i%k)==0)
	    {
	        data = temp->data;
	    }
	   
	    temp=temp->next;
	     i++;
	}
	
	if(data == -1)
	return -1;
	else return data;
}


```
