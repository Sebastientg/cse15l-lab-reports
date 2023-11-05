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

Example 1: The command is seaching the string "Salt Lake City" in all text files within the current directory and its subdirectories. This is useful when wanting to make a simple search without any paths in the argument. 

*Input* 
```
grep -r "Salt Lake City"
```

*Output*
```
./technical/government/Env_Prot_Agen/jeffordslieberm.txt:Air & Waste Management Association, Salt Lake City, June 18-22,
./technical/government/Media/It_Pays_to_Know.txt:Salt Lake City Tribune
./technical/government/Media/It_Pays_to_Know.txt:Glendale Senior Housing in Salt Lake City last month, she moved to
./technical/government/Media/It_Pays_to_Know.txt:Meanwhile, Sweat's granddaughter called Salt Lake City housing
./technical/government/Media/The_State_of_Pro_Bono.txt:Alan Sullivan of the Salt Lake City office of Phoenix's Snell
./technical/government/Media/5_Legal_Groups.txt:Salt Lake City Tribune
./technical/biomed/1471-2172-4-1.txt:          BioScience, Salt Lake City, UT). For experiments
./technical/biomed/1472-6947-2-7.txt:          Intermountain Health Care in Salt Lake City, Wishard
./technical/biomed/1471-2369-3-6.txt:        Regional University Pathologists, Salt Lake City, UT) in
./technical/biomed/1471-2180-2-38.txt:        Microbiology Meeting, Salt Lake City, May 2002
```

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
