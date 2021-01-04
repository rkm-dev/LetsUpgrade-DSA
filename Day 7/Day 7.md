# Day 7 - Assignment

### Q1.  Write a program implementing insert, delete and display operation of Circular Queue.

```C
#include <stdio.h>
#include <stdlib.h>
#define max 5

int cqArr[max];
int front = -1;
int rear  = -1;

void insert(int x);
void del();
void display();

int main()
{
    int choice,item;
    do {
        printf("\nEnter your choice - ");
        printf("\n1.Insert");
        printf("\n2.Delete");
        printf("\n3.Display");
        printf("\n4.Quit");
        printf("\nEnter your choice : ");
        scanf("%d",&choice);

        switch(choice) {
            case 1 :
                printf("\n Input the element for insertion in queue : ");
                scanf("%d", &item);
                insert(item);
                break;
            case 2 :
                del();
                break;
            case 3:
                display();
                break;
            case 4:
                break;
            default:
                printf("\nInvalid input");
        }
    }while(choice!=4);
    return 0;
}

void insert(int x)
{
    if((front == 0 && rear == max-1)||(front == rear+1)) {
        printf("\n Queue is Full");
        return -1;
    }

    if(front == -1) {
        front = 0;
        rear  = 0;
    } else {
        if(rear == max-1)
            rear = 0;
        else
            rear+=1;
    }
    cqArr[rear]=x;
}

void del()
{
    if(front == -1) {
        printf("\n Queue Empty");
        return -1;
    }

    printf("Deleted element from the front of queue : %d ", cqArr[front]);
    if(front == rear) {
        front = -1;
        rear  = -1;
    } else {
        if(front == max-1)
            front = 0;
        else
            front = front+1;
    }
}

void display()
{
    int fpos = front, rpos = rear;
    if(front == -1) {
        printf("\n Queue is empty");
        return -1;
    }
    printf("\n Queue : ");
    if(fpos <= rpos) {
        while(fpos <= rpos) {
            printf("%d ", cqArr[fpos]);
            fpos++;
        }
    } else {
        while(fpos <= max-1) {
            printf("%d ", cqArr[fpos]);
            fpos++;
        }
        fpos = 0;
        while(fpos <= rpos) {
            printf("%d ", cqArr[fpos]);
            fpos++;
        }
    }
    printf("\n");
}

```