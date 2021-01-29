# [Implement Stack using Linked List ](https://practice.geeksforgeeks.org/problems/implement-stack-using-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=-2&difficulty[]=-1&page=1&query=category[]Linked%20Listdifficulty[]-2difficulty[]-1page1category[]Linked%20List)
<p>Let's give it a try! You have a linked list and you have to implement the functionalities push and pop of stack using this given linked list. Your task is to use the class as shown in the comments in the code editor and complete the functions push() and pop() to implement a stack. </p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">push(2)
push(3)
pop()
push(4) 
pop()</span>
<strong>Output: </strong><span id="example-output-1"> 3, 4
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">pop()
push(4)
push(5)
pop()</span>
<strong>Output: </strong><span id="example-output-1"> -1 5 
</pre>


</div>
</div>

```cpp
void MyStack ::push(int a) {
    // base case
    if (top == NULL) {
        top = new StackNode(a);
    } else {

        // create a temp node in the stack
        StackNode *temp = new StackNode(a);

        // assign top and the next to current
        temp->next = top;

        top = temp;
    }
}

/*The method pop which return the element poped out of the stack*/
int MyStack ::pop() {
    StackNode *temp = top;

    // base case
    if (temp == NULL) {
        return -1;
    } else {
        // deleting node from linked list
        temp = temp->next;
        int r = top->data;
        delete (top);
        top = temp;
        return r;
    }
}

```
