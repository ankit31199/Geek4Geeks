```cpp

// head : reference to head of linked list

int getCount(struct Node* head){
    int count =0;
    while(head)
    {
        count++;
        head=head->next;
    }
return count;
    

}

```  
