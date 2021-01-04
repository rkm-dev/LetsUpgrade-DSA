# Day 3 - Assignment

### Q1. Write a function “insert_any()” for inserting a node at any given position of the linked list. Assume position starts at 0.

```C
node *insert_any(node *head, int val, int pos)
{
    int i;
    node *new = create(val);
    node *temp = head;
    //if position 1 then insert at beginning
    if(pos==1)
    {
        new->next=temp;
        head=new;
        return head;
    }
    for(i=0;i<pos-2;i++)
    {
        temp=temp->next;
        if(temp==NULL)      // to check for the current position is valid or not
        {
            printf("\nPosition out of bound");
            return head;
        }
    }
    new->next=temp->next;
    temp->next=new;
    printf("\n node inserted");
    return head;
}
```

### Q2. Write a function “delete_beg()” for deleting a node from the beginning of the linked list

```C
node *delete_beg(node *head)
{
    if(head == NULL)
    {
        printf("\nEmpty List");
    }
    node *temp = head;
    head = temp->next;
    free(temp);
    return head;
}
```

### Q3. Write a function “delete_end()” for deleting a node from the end of the linked list.

```C
node *delete_end(node *head)
{
    if(head == NULL)
    {
        printf("\nEmpty List");
    }
    else if(head->next==NULL)
    {
        head == NULL;
        free(head);
        printf("\n Node Deleted, List now empty");
    }
    else
    {
        node *temp = head, *temp1;
        while(temp->next)
        {
            temp1 = temp;
            temp = temp->next;
        }
        temp1->next=NULL;
        free(temp);
        printf("\nLast Node deleted");
    }
    return head;
}
```

## Linked List Program

```C
#include <stdio.h>
#include <stdlib.h>

typedef struct node
{
    int data;
    struct node *next;
}node;

node *create(int x);
node *insert_end(node *head, int x);
node *insert_beg(node *head, int x);
node *insert_any(node *head, int val, int pos);
node * delete_beg(node *head);
node *delete_end(node *head);
void print(node *head);

int main()
{
    node *head = NULL;
    head = insert_end(head, 10);
    head = insert_beg(head, 12);
    head = insert_end(head, 15);
    head = insert_beg(head, 20);
    head = insert_end(head, 30);
    head = insert_beg(head, 45);
    print(head);

    head = insert_beg(head, 15);
    print(head);

    int val, pos;
    printf("\n Enter the value to be inserted : ");
    scanf("%d",&val);

    printf("\n Enter the position for insertion : ");
    scanf("%d",&pos);

    head = insert_any(head, val, pos);
    print(head);

    printf("\n Deleting element at the beginning");
    head = delete_beg(head);
    print(head);

    printf("\n Deleting element at the End");
    head = delete_end(head);
    print(head);
}

// create a new node
node *create(int x)
{
    node *new = (node *)malloc(sizeof(node));
    new->data = x;
    new->next=NULL;
    return new;
}

//insert at the end
node *insert_end(node *head, int x)
{
    node *new = create(x);
    node *temp = head;

    if(head==NULL)
    {
        head = new;
        return head;
    }
    while(temp->next)
    {
        temp=temp->next;
    }
    temp->next=new;
    return head;
}

//insert at beginning
node * insert_beg(node *head, int x)
{
    node *new = create(x);
    new->next=head;
    head=new;
    return head;
}

//printing the list
void print(node *head)
{
    node *temp = head;
    printf("\nList : ");
    while(temp)
    {
        printf("%d ",temp->data);
        temp=temp->next;
    }
    printf("\n");
}

node *insert_any(node *head, int val, int pos)
{
    int i;
    node *new = create(val);
    node *temp = head;
    if(pos==1)
    {
        new->next=temp;
        head=new;
        return head;
    }
    for(i=1;i<pos-1;i++)
    {
        temp=temp->next;
        if(temp==NULL)
        {
            printf("\nPosition out of bound");
            return head;
        }
    }
    new->next=temp->next;
    temp->next=new;
    printf("\n node inserted");
    return head;
}

node *delete_beg(node *head)
{
    if(head == NULL)
    {
        printf("\nEmpty List");
    }
    node *temp = head;
    head = temp->next;
    free(temp);
    return head;
}

node *delete_end(node *head)
{
    if(head == NULL)
    {
        printf("\nEmpty List");
    }
    else if(head->next==NULL)
    {
        head == NULL;
        free(head);
        printf("\n Node Deleted, List now empty");
    }
    else
    {
        node *temp = head, *temp1; //temp for current node and temp1 for previous node
        while(temp->next)
        {
            temp1 = temp;
            temp = temp->next;
        }
        temp1->next=NULL;
        free(temp);
        printf("\nLast Node deleted");
    }
    return head;
}

```

