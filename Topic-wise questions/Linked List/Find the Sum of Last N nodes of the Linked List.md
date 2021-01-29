# [Find the Sum of Last N nodes of the Linked List ](https://practice.geeksforgeeks.org/problems/find-the-sum-of-last-n-nodes-of-the-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List) 
<p>Given a single linked list of size M, your task is to complete the function sumOfLastN_Nodes(), which should return the sum of last N nodes of the linked list.  
  Input:
The function takes two arguments as input, the reference pointer to the head of the linked list and the an integer N.
There will be T test cases and for each test case the function will be called seperately.


Output:
For each test case output the sum of last N nodes of the linked list.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">2
6 3
5 9 6 3 4 10
2 2
1 2</span>
<strong>Output: </strong><span id="example-output-1">   17
3
</pre>




</div>
</div>

```cpp
int sumOfLastN_Nodes(struct Node* head, int n)
{
         // if n == 0
    if (n <= 0)
        return 0;
 
    int sum = 0, temp = 0;
    struct Node* ref_ptr, *main_ptr;
    ref_ptr = main_ptr = head;
 
    // traverse 1st 'n' nodes through 'ref_ptr' and
    // accumulate all node's data to 'sum'
    while (ref_ptr != NULL &&  n--) {                   
        sum += ref_ptr->data;
 
        // move to next node
        ref_ptr = ref_ptr->next;
    }
 
    // traverse to the end of the linked list
    while (ref_ptr != NULL) {
 
        // accumulate all node's data to 'temp' pointed
        // by the 'main_ptr'
        temp += main_ptr->data;
 
        // accumulate all node's data to 'sum' pointed by
        // the 'ref_ptr'
        sum += ref_ptr->data;
 
        // move both the pointers to their respective
        // next nodes
        main_ptr = main_ptr->next;
        ref_ptr = ref_ptr->next;
    }
 
    // required sum
    return (sum - temp);
}
```
