 void deleteAlt(struct Node *head){
     Node *temp,*p;
     if(head==NULL)
     return ;
     temp=head;
     p=head->next;
     while((temp!=NULL)&&(p!=NULL))
     {
         temp->next=p->next;
         delete p;
         temp=temp->next;
         if(temp!=NULL)
         p=temp->next;
     }
    
         
     }
