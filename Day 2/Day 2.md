# Day 2 - Assignment

###  Q1. Write the program for deleting an element from the beginning and from any position.
```C
/*
    array         : arr[]
    size of array : n
*/
/* Deleting from Beginning */
/* transfering the value of [i+1]th element to [i]th element */

for(i=0; i<n-1; i++)
{
    arr[i] = arr[i+1]; 
} 
n--;   /* Decrementing the size of the initial array */
```
## --------------------------------------------------------------------------------------------------------
```C
/* Deleting from any position k */
/* transfering the value of [i+1]th element to [i]th element */

if(k>0)
{
    for(i=k-1; i<n-1; i++)
    {
        arr[i] = arr[i+1];
    }
    n--;   /* Decrementing the size of the initial array */
}
```

### Q2. Write the program for printing the array after rotating it k times towards left, where k would be taken as user input.
```C
/*
    array           : arr[]
    size            : n
    No. of rotation : k
*/

void rotateLeft(int arr[], int n, int k) 
{ 
    int i=0;
    while(i<k)
    {
        int j, temp = arr[0]; 
        for (j=0; j<n-1; j++)
        {
            arr[j] = arr[j+1];
        }
        arr[j] = temp;
        i++;
    }   
}
```
