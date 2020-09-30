# XXXXX
DSA
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *next;
}*start=NULL;
void nor_insert()
{
    struct node *t = (struct node*)malloc(sizeof(struct node));
    printf("Enter Data: ");
    scanf("%d",&t->data);
    t->next=NULL;
    if(start==NULL)
    {
        start = t;
    }
    else
    {
        struct node *q = start;
        while(q->next!=NULL)
            q = q->next;
        q->next = t;
    }
}
void beg_insert()
{
    struct node *t = (struct node*)malloc(sizeof(struct node));
    printf("Enter Data: ");
    scanf("%d",&t->data);
    t->next = start;
    start = t;
}
void end_insert()
{
    struct node *t = (struct node*)malloc(sizeof(struct node));
    printf("Enter Data: ");
    scanf("%d",&t->data);
    t->next = NULL;
    if(start == NULL)
        start = t;
    else
    {
        struct node *q = start;
        while(q->next!=NULL)
            q = q->next;
        q->next = t;
    }
}
void pos_insert()
{
    struct node *t = (struct node*)malloc(sizeof(struct node));
    int n;
    printf("Enter Position: ");
    scanf("%d",&n);
    t->next=NULL;
    struct node *q = start;
    if(start==NULL && n==1)
        start = t;
    else if(start!=NULL && n==1)
    {
        printf("Enter Data: ");
        scanf("%d",&t->data);
        t->next = start;
        start = t;
    }
    else
    {
        for(int i=1;i<n-1;i++)
        {
            q = q->next;
            if(q==NULL)
            {
                printf("Operation can't be done!\n");
                return;
            }
        }
        printf("Enter Data: ");
        scanf("%d",&t->data);
        t->next = q->next;
        q->next = t;
    }
}
void aft_insert()
{
    struct node *t = (struct node*)malloc(sizeof(struct node));
    int n,m;
    printf("Enter Element: ");
    scanf("%d",&n);
    printf("Element To enter: ");
    scanf("%d",&t->data);
    t->next=NULL;
    struct node *q = start;
    while(q->data!=n)
    {
        q = q->next;
        if(q==NULL)
        {
            printf("Operation can't be done!\n");
            return;
        }
    }
    t->next = q->next;
    q->next = t;
}
void display()
{
    struct node *q = start;
    if(q==NULL)
        printf("LL is Empty!");
    else
    {
        while(q!=NULL)
        {
            printf("%d ",q->data);
            q = q->next;
        }
    }
}
void main()
{
    display();
}
