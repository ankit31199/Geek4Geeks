# [Insert in Middle of Linked List  ](https://practice.geeksforgeeks.org/problems/insert-in-middle-of-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-1page1category[]Linked%20List)
<p>Given a linked list of size N and a key. The task is to insert the key in the middle of the linked list.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList = 1->2->4
key = 3</span>
<strong>Output: </strong><span id="example-output-1"> 1 2 3 4
</pre>


</div>
<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">LinkedList = 10->20->40->50
key = 30</span>
<strong>Output: </strong><span id="example-output-1"> 10 20 30 40 50
</pre>


</div>

```cpp
Node* insertInMiddle(Node* head, int x)
{
	// if list is empty
	if (head == NULL)return (new Node(x));
	else {
		Node* newNode = new Node(x);    // Make a new node
		Node* slow = head;
		Node* fast = head->next;        
		while (fast && fast->next) {  
			slow = slow->next;          // When fast will reach end, slow will be at the mid point
			fast = fast->next->next;    // Make fast moves two nodes at a time
		}
		newNode->next = slow->next;     // Make the newNode next as slow next
		slow->next = newNode;           // Make slow next as newNode
	}
	return head;
}
