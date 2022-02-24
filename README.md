# queue-linked-list

#include<stdio.h>
#include<stdlib.h>
struct queues
{
    int data;
    struct queues *next;
};
typedef struct queues node;
node *front=NULL,*rear=NULL;
void enqueue(int k)
{
    node *new;
    new=(node*)malloc(sizeof(node));
    new->data=k;
    new->next=NULL;
    if (front==NULL)
    {
        front=new;
        rear=new;
    }
    else
    {
        rear->next=new;
        rear=new;
    }
   
}
int dequeue()
{
    node *temp;
    int x;
    if (front==NULL)
    {
        return -1;
    }
    else
    {
        if (front==rear)
        {
            front=NULL;
            rear=NULL;
        }
        else
        {
        temp=front;
        x=temp->data;
        front=front->next;
        free(temp);
        }
    }
}
void display()
{
    node *k;
    k=front;
    while(k!=NULL)
    {
        printf("%d",k->data);
        k=k->next;
    }
}
void main()
{
    int c,k;
    while(1)
    {
        printf("enter c:");
        scanf("%d",&c);
        switch(c)
        {
            case 1:printf("enter k:");
                   scanf("%d",&k);
                   enqueue(k);
                   break;
            case 2:dequeue();
                   break;
            case 3:display();
                   break;
            case 4:exit(0);
           
        }
    }
}
output:
enter c:1
enter k:5
enter c:2
enter c:1
enter k:7
enter c:3
7enter c:4
