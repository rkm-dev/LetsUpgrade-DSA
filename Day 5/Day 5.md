# Day 5 - Assignment

### Q1. Write the function for insertion sort.

```C
int insertionSort(int a[])
{
    int i, j, temp;
    for(i=1;i<n;i++) {
        temp = a[i];
        j = i-1;
        while(j>=0 && a[j]>temp) {
            a[j+1] = a[j];
            j--;
        }
        a[j+1] = temp;
    }
    return a;
}
```