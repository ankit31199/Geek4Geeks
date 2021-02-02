# [Absolute List Sorting  ](https://practice.geeksforgeeks.org/problems/absolute-list-sorting/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given a linked list L of N nodes, sorted in ascending order based on the absolute values of its data. Sort the linked list according to the actual values.
Ex: Input : 1 -> -2 -> -3 -> 4 -> -5 
      Output: -5 -> -3 -> -2 -> 1 -> 4

Input
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case consists of two lines. The first line of each test case contains a positive integer N denoting the size of linked list. The second line of each test case contains N space separated integers denoting the values of N nodes.


Output
Corresponding to each test case, the expected output will be space separated values of the sorted linked list.


Constraints
1 <= T <= 100
0 <   N  <= 30
-100 <= L[i] <= 100</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">2
3
1 -3 -4
4
0 -2 3 -10</span>
<strong>Output: </strong><span id="example-output-1"> -4  -3  1
-10 -2  0  3
</pre>


</div>

```cpp
void sortList(Node** head)
{
   
    Node *p,*c;
    p=*head;
    c=(*head)->next;
    while(c!=NULL)
    {
        if(p->data>c->data)
        {
            p->next=c->next;
            c->next=*head;
            *head=c;
            
            c=p;
        }
        else 
        {
            p=c;
        }
        c=c->next;
    }
}
