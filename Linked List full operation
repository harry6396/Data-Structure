#include <stdio.h>
#include<stdlib.h>
struct ll{
    int data;
    struct ll *link;
};
void addnodes(struct ll*,int);
void display(struct ll*);
void reverse(struct ll**);
void even(struct ll*,int);
void odd(struct ll*,int);
void search(struct ll*,int);
void delete(struct ll**,int);
void begin(struct ll**,int);
void btw(struct ll*,int,int);
void deletes(struct ll*);
int main() {
    int i,n,choice=0,a,b;
    printf("Enter the number of nodes\n");
    scanf("%d",&n);
    struct ll *start=NULL;
    printf("Enter the choice\n1.Addnodes\n2.Display\n3.Reverse\n4.Even Nodes\n5.Odd Nodes\n6.Search\n7.Delete\n8.Add at begining\n9.Add at any position\n10.Exit\n");
    while (choice!=10) {
        scanf("%d",&choice);
        switch (choice) {
            case 1:
                start=malloc(sizeof(struct ll));
                scanf("%d",&a);
                start->data=a;
                start->link=NULL;
                for(i=1;i<n;i++){
                    scanf("%d",&a);
                    addnodes(start,a);
                }
                break;
                
            case 2:
                display(start);
                break;
            case 3:
                reverse(&start);
                display(start);
                break;
            case 4:
                even(start, n);
                break;
            case 5:
                odd(start, n);
                break;
            case 6:
                printf("Enter the element to be searched\n");
                scanf("%d",&a);
                search(start, a);
                break;
            case 7:
                printf("Enter the number to be deleted\n");
                scanf("%d",&a);
                delete(&start, a);
                display(start);
                break;
            case 8:
                scanf("%d",&a);
                begin(&start, a);
                break;
            case 9:
                printf("Enter the position you want to insert at\n");
                scanf("%d",&b);
                printf("Enter the data\n");
                scanf("%d",&a);
                btw(start,a,b);
                break;
        }
    }
    deletes(start);
    display(start);
    return 0;
}
void addnodes(struct ll*q,int a){
    struct ll *p;
    while (q->link!=NULL)
        q=q->link;
    p=malloc(sizeof(struct ll));
    p->data=a;
    p->link=q->link;
    q->link=p;
}
void display(struct ll *q){
    if(q==NULL)
      printf("First add some nodes\n");
    else{
    while(q!=NULL)
    {
        printf("%d ",q->data);
        q=q->link;
    }
    printf("\n");
     }
}
void search(struct ll *q,int a){
    int count=1;
    struct ll *temp=q;
    while(temp!=NULL){
        if(a==temp->data)
            printf("Found Element at node:- %d\n",count);
        count++;
        temp=temp->link;
 }
}
void odd(struct ll *q,int n){
    int i;
    for(i=1;i<=n;i++){
        if(i%2==1)
            printf("%d ",q->data);
        q=q->link;
    }
    printf("\n");
}
void even(struct ll *q,int n){
    int i;
    for(i=1;i<=n;i++){
        if(i%2==0)
            printf("%d ",q->data);
        q=q->link;
    }
    printf("\n");
}
void reverse(struct ll **q){
    struct ll *temp,*p=NULL,*x;
    temp=*q;
    while (temp!=NULL) {
        x=p;
        p=temp;
        temp=temp->link;
        p->link=x;
    }
    *q=p;
}
void delete(struct ll **q,int a)
{
    struct ll *temp=*q,*p=*q;
    while(temp!=NULL){
        if(temp->data==a)
        {
            if (temp==*q)
                *q=temp->link;
            else
                p->link=temp->link;
            free(temp);
        }
        else{
            p=temp;
            temp=temp->link;
        }
    }
}
void begin(struct ll**q,int a){
    struct ll *p;
    p=malloc(sizeof(struct ll));
    p->data=a;
    p->link=*q;
    *q=p;
}
void btw(struct ll *q,int a,int b){
    struct ll *p,*temp=q;
    int i;
    for(i=1;i<b-1;i++)
        temp=temp->link;
    if(temp==NULL)
        printf("Sorry not possible\n");
    else{
        p=malloc(sizeof(struct ll));
        p->data=a;
        p->link=temp->link;
        temp->link=p;
    }
}
void deletes(struct ll *q)
{
    struct ll *p=q,*temp;
    while(p!=NULL)
    {
        temp=p->link;
        if(p->data==temp->data)
        {
            q=temp;
            p->link=temp->link;
            free(q);
        }
        p=p->link;
    }
}
