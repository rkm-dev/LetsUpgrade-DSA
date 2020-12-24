# Day 1 - Assignment

### Q1. 

`for(i=1; i<=n; i++) {
    for(j=i; j<=n; j++) {
        printf("hi")
    }
}`

> So the outer loop will run for `n` times so `O(n)`

> The inner loop however will run `n-i` times

> The total number of times the execution happens can be imagined and counted in reverse, so in the last there is one time operation running then before that it will be 2 times then before that 3 times and so on for n times

> so basically total number of times of operation can be laid out as following:

>>    `1+2+3+4+5+...+n = n(n+1)2` = `n^2/2 + n/2` 

>>    so time complexity will be `O(n^2/2 + n/2)` or `O(n^2)` or `O(n*n)`   

### Q2.

`for(i=1; i<=n; i=*3) {
    for(j=1; j<=n; j++) {
        printf('hello')
    }
}`

> The outer loop will have time complexity of log n (Base-3 logarithm) so O(log n)

> Inner loop not affected by the outer loops value so O(n)

>> T(n) = O(logn) x O(n) = O(n logn)


```python

```
