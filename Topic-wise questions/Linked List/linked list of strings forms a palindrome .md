# [linked list of strings forms a palindrome ](https://practice.geeksforgeeks.org/problems/linked-list-of-strings-forms-a-palindrome/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given a linked list of strings having n nodes check to see whether the combined string formed is palindrome or not. 

Input:
You have to complete the method which takes one argument: the head of the linked list . You should not read any input from stdin/console.. There are multiple test cases. For each test case, this method will be called individually.

Output:
Your function should return True if the combined string is pallindrome else it should return False.

User Task:
The task is to complete the function compute() which returns true or false.

Constraints:
1 <=T<= 103  
1 <=n<= 103</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1"> 
2
5
a bc d dcb a
4
a bc d ba</span>
<strong>Output: </strong><span id="example-output-1"> 
True
False
</pre>


</div>

```cpp
bool ispalin(string str)
{
    int length=str.size();
    for(int i=0,j=length-1;i<length;i++,j--)
    {
        if(str[i]!=str[j])
        {
            return false; 
        }
    }
    return true;
}
bool compute(Node* root)
{
   //Your code goes here
   string str="";
   Node *front,*rear;
   front=rear=root;
   int flag=0;
   while(rear)
   {
       str.append(rear->data);
       rear=rear->next;
   }
   return ispalin(str);
}
   
