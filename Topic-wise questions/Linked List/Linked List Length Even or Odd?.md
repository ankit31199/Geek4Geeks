
// Function should return 0 is length is even else return 1

int isLengthEvenOrOdd(struct Node* head)
{
     int count =0;
     while(head)
     {
         count++;
         head=head->next;
     }
     if((count%2)!=0)
     return 1;
     else 
     return 0;
}
