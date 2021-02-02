# [Merge Sort for Linked List ](https://practice.geeksforgeeks.org/problems/sort-a-linked-list/1/?category[]=Linked%20List&category[]=Linked%20List&difficulty[]=0&page=1&query=category[]Linked%20Listdifficulty[]0page1category[]Linked%20List)
<p>Given Pointer/Reference to the head of the linked list, the task is to Sort the given linked list using Merge Sort.
Note: If the length of linked list is odd, then the extra node should go in the first list while splitting.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">N = 5
value[]  = {3,5,2,4,1}</span>
<strong>Output: </strong><span id="example-output-1"> 1 2 3 4 5
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">N = 3
value[]  = {9,15,0}
</span>
<strong>Output: </strong><span id="example-output-1"> 0 9 15
</pre>


</div>
</div>

```cpp
void splitList(Node* source, Node** frontRef,
               Node** backRef) {
    struct Node* fast;
    struct Node* slow;
    if (source == NULL || source->next == NULL) {
        *frontRef = source;
        *backRef = NULL;
    } else {
        slow = source;
        fast = source->next;
        while (fast != NULL) {
            fast = fast->next;
            if (fast != NULL) {
                slow = slow->next;
                fast = fast->next;
            }
        }
        *frontRef = source;
        *backRef = slow->next;
        slow->next = NULL;
    }
}

Node* mergeList(struct Node* a, struct Node* b) {
    struct Node* result = NULL;
    if (a == NULL)
        return (b);
    else if (b == NULL)
        return (a);
    if (a->data <= b->data) {
        result = a;
        result->next = mergeList(a->next, b);
    } else {
        result = b;
        result->next = mergeList(a, b->next);
    }
    return (result);
}

Node* mergeSort(Node *head) {
    
    struct Node* a;
    struct Node* b;
    if (head == NULL || head->next == NULL) return head;
    splitList(head, &a, &b);
    a = mergeSort(a);
    b = mergeSort(b);
    return mergeList(a, b);
}
}

