# Day 1 - Assignment

### Q1. Write the program for deleting an element from the beginning and from any position.

/* 
	array         : arr[]
	size of array : n
*/

/* Deleting from Beginning */
/* transfering the value of [i+1]th element to [i]th element */

		for(i=0; i<n; i++)
		{
			arr[i] = arr[i + 1];
		}
/* Decrementing the size of the initial array */
		n--;

--------------------------------------------------------------------------------

/* Deleting from any position k */
/* transfering the value of [i+1]th element to [i]th element */

   if(k>0)
   {
		for(i=k-1; i<n; i++)
		{
			arr[i] = arr[i + 1];
		}
/* Decrementing the size of the initial array */
		n--;
	}

### Q2. Write the program for printing the array after rotating it k times towards left, where k would be taken as user input.

