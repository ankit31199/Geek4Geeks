# [Count Pairs whose sum is equal to X ](https://practice.geeksforgeeks.org/problems/count-pairs-whose-sum-is-equal-to-x/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given two linked list of size N1 and N2 respectively of distinct elements, your task is to complete the function countPairs(), which returns the count of all pairs from both lists whose sum is equal to the given value X.
Note: The 2 numbers of a pair should be parts of different lists..</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">L1 = 1->2->3->4->5->6
L2 = 11->12->13
X = 15</span>
<strong>Output: </strong><span id="example-output-1"> 3
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">L1 = 7->5->1->3
L2 = 3->5->2->8
X = 10</span>
<strong>Output: </strong><span id="example-output-1"> 2
</pre>


</div>
</div>

```cpp
int countPairs(struct Node* head1, struct Node* head2, int x) {
   unordered_set<int> s; 
   int count=0;
   while(head1!=NULL)
   {
       s.insert(head1->data);
       head1=head1->next;
   }
   while(head2!=NULL)
   {
       if(s.find(x-head2->data)!=s.end())
       {
           count++;
       }
       head2=head2->next;
   }
   return count;
}
