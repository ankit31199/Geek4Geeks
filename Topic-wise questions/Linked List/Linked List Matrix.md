# [Linked List Matrix ](https://practice.geeksforgeeks.org/problems/linked-list-matrix/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given a Matrix mat of N*N size, the task is to complete the function constructLinkedMatrix(), that constructs a 2D linked list representation of the given matrix.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">2D matrix 
1 2 3
4 5 6
7 8 9</span>
<strong>Output: </strong><span id="example-output-1">
1 -> 2 -> 3 -> NULL
|    |    |
v    v    v
4 -> 5 -> 6 -> NULL
|    |    |
v    v    v
7 -> 8 -> 9 -> NULL
|    |    |
v    v    v
NULL NULL NULL
</pre>


</div>

```cpp
Node* cons(int mat[MAX][MAX],int i,int j, int n)
{
    if(i>n-1||j>n-1)
    return NULL;
    else 
    {
        Node *temp=new Node(mat[i][j]);
        temp->right=cons(mat,i,j+1,n);
        temp->down=cons(mat,i+1,j,n);
        return temp;
        
    }
}

Node* constructLinkedMatrix(int mat[MAX][MAX], int n)
{
  int i=0,j=0;
  return cons(mat,i,j,n);
 
}
