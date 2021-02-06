# [Compare two linked lists  ](https://practice.geeksforgeeks.org/problems/compare-two-linked-lists/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given two string, represented as linked lists (every character is a node->data in the linked list). Write a function compare() that works similar to strcmp(), i.e., it returns 0 if both strings are same, 1 if first linked list is lexicographically greater, and -1 if second is lexicographically greater.

Input:
First line of input contains number of testcases T. For each testcase, there will be 4 lines of input. First line of which contains length of first linked list and next line contains the linked list, similarly next two lines contains length and linked list respectively.

Output:
Comapare two strings represented as linked list.

User Task:
The task is to complete the function compare() which compares the strings through linked list and returns 0, 1 or -1 accordingly.

Constraints:  
1 <= T <= 100
1 <= N, M <= 100</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">
2
5
a b a b a
4
a b a a
3
a a b
3
a a b</span>
<strong>Output: </strong><span id="example-output-1"> 
1
0
</pre>


</div>

```cpp
int count(Node *head)
{
    int co=0;
    while(head)
    {
        head=head->next;
        co++;
    }
    return co;
}

int compare(Node *list1, Node *list2) 
{
    
     Node *temp1,*temp2;
     int count1,count2,counter=0;;
     count1=count(list1);
     count2=count(list2);
    
         while(list1)
         {
             if(list1->c == list2->c)
             {
                 counter++;
             }
             else if(list1->c > list2->c)
             {
                 return 1;
             }
             else if(list1->c < list2->c)
             {
                 return -1;
             }
             list1=list1->next;
             list2=list2->next;
         }
         if(counter == count1)
         {
             return 0;
         }
     }
