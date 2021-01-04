# Day 6 - Assignment

### Q1. Write a function to find the maximum element in the stack.

### Q2. Write a function to find the minimum element in the stack.

```C
#include <stdio.h>
#include <stdlib.h>

int data[10], top, max=0, min=0;
void push(int x)
{
   top++;
   data[top]=x;
   if(max < data[top])
        max = data[top];
   if(min > data[top])
        min = data[top];
}

void pop()
{
    int i;
    if(max == data[top])
        max=0;
    if(min == data[top])
        min=0;
    printf("\n Top element deleted from the stack : %d",data[top]);
    top--;
    for(i= top;i>=0;i--) {
     if(max < data[i])
        max = data[i];
     if(min > data[i])
        min = data[i];
    }
}
int main()
{
    int elem, choice;
    top = -1;
    do
    {
        printf("\n Choose one of the options");
        printf("\n 1. Push an element\n 2. Pop an element\n 3. Display max value in the stack\n 4. Display min value in the stack");
        printf("\n 5. Quit \n Enter your choice : ");
        scanf("%d ",&choice);
        switch(choice)
        {
            case 1:
                printf("\n Enter a number to be pushed into the stack : ");
                scanf("%d ",&elem);
                push(elem);
                break;
            case 2:
                pop();
                break;
            case 3:
                printf("\n The current Max value in the stack is : %d",max);
                break;
            case 4:
                printf("\n The current Min value in the stack is : %d",min);
                break;
            case 5:
                printf("\n Quit");
                break;
            default:
                printf("\nInvalid input");
        }
    }while(choice!=5);
    return 0;
}

```