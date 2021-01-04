# Day 4 - Assignment

### Q1. In the Binary Search algorithm, it is suggested to calculate the mid as beg + (end - beg) / 2 instead of (beg + end) / 2. Why is it so?

#### Ans. mid = (beg+end)/2 is a correct logic in majority of the cases but if (beg+end) approches maximum int size it may yield -1 as a result of integer capacity overflow, which will as a result cause error in the mid point claculation. 
#### So it is suggested to use mid = beg+(end-beg)/2 as it avoids any condition for integer overflow.

### Q2. Write the algorithm/function for Ternary Search.

```C
int ternarySearch(int arr[], int key, int start, int end)
{
    if(end-start > 0) {
        int firstMid  = start + (end - start)/3; // first mid point
        int secondMid = firstMid + (end - start)/3; //second mid point
        
        if(arr[firstMid] == key) {
            return firstMid;
        }
        
        if(arr[secondMid] == key) {
            return secondMid;
        }
        
        if(key < arr[firstMid]) {
            return ternarySearch(arr, key, start, firstMid);
        }
        
        if(key > arr[secondMid]) {
            return ternarySearch(arr, key, secondMid+1, end);
        }
        
        return ternarySearch(arr, key, firstMid, secondMid);
    } else {
        return -1;
    }
}
```