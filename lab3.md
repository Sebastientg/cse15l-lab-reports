# Lab Report 3

## Part 1 - Bugs 
Array data structure code of reversing and integer type array: 
The original code contains a bug when attempting to reverse an array. When the code assigns arr[i] to a new value, the original value is overwritten before it is assigned to the correct position. To fix this issue the new code uses two pointers to to switch the values from start to end. This way, the elements are correctly reversed in place without overwriting their original values. 

Before Code: 
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
Fixed Code: 
```
static void reverseInPlace(int[] arr) {
    int start = 0;
    int end = arr.length-1; 
    while (start < end) {
      int value = arr[start]; 
      arr[start] = arr[end];
      arr[end] = value; 
      start = start + 1; 
      end = end - 1; 
    }

  }
```

## Part 2 - Researching Commands - "Grep"

__1. grep with -r__
Example 1:

Example 2:
 
__2. grep with -n__
Example 1:

Example 2:   
   
__3. grep with -e__
Example 1:

Example 2:   
   
__4. grep with -l__
Example 1:

Example 2:   
