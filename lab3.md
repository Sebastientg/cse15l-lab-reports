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

Example 1: The command is seaching the string "Salt Lake City" in all text files within the current directory and its subdirectories. This is useful when wanting to make a simple search without any paths in the argument. This command returns the lines with the given string and the paths. 

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

Example 2: The command is searching the path ./technical/government to find search for the string "executive guide." This command is useful when wanting to search a specific string in a specific directory or subdirectory. 

*Input*
```
grep -r "executive guide" ./technical/government
```

*Output*
```
./technical/government/Gen_Account_Office/d0269g.txt:This executive guide is intended to identify effective practices
./technical/government/Gen_Account_Office/d0269g.txt:This executive guide was prepared under the direction of Linda
./technical/government/Gen_Account_Office/d0269g.txt:In this executive guide, we highlight many of the strategic
./technical/government/Gen_Account_Office/d0269g.txt:6this executive guide focuses on internal controls as
./technical/government/Gen_Account_Office/d0269g.txt:draft of this executive guide to obtain comments from interested
./technical/government/Gen_Account_Office/Testimony_cg00010t.txt:in GAO's executive guides have been incorporated into policy
./technical/government/Gen_Account_Office/d01376g.txt:their practices and assisting us in producing this executive guide.
./technical/government/Gen_Account_Office/d01376g.txt:This executive guide includes examples from our case study
./technical/government/Gen_Account_Office/gg96118.txt:In this executive guide, we discuss the three key steps and
./technical/government/Gen_Account_Office/gg96118.txt:with each step.6 In the final section of this executive guide, we
./technical/government/Gen_Account_Office/gg96118.txt:executive guide are largely a synthesis of previously published
./technical/government/Gen_Account_Office/ai00134.txt:executive guide is intended to assist federal agencies in achieving
./technical/government/Gen_Account_Office/ai00134.txt:This executive guide was prepared under the direction of Lisa G.
./technical/government/Gen_Account_Office/ai00134.txt:executive guide, along with our 1998 report on the training and
```

__2. grep with -n__

Example 1: The command searches for a specfic string, given a path to a specific file, to return the line where that string is located along with the string contents of that line. This is useful when wanting to find the line number/s of a specific string in a file. 

*Input*
```
grep -n "asemissions" ./technical/government/Env_Prot_Agen/bill.txt
```

*Output*
```
6979:cost-effectively asemissions from each other principal category of
```

Example 2: The command is searching for string with a given path. The additional H to the -n commands the terminal to return an output that displays the path, including the file name, along with the line number and line the string is in. This is useful when wanting an output that displays the file where the string is in and its line number and line.  

*Input*
```
grep -nH "coastal ecosystems" ./technical/government/Env_Prot_Agen/final.txt
```

*Output*
```
./technical/government/Env_Prot_Agen/final.txt:53:freshwater and coastal ecosystems would be likely. Public health
./technical/government/Env_Prot_Agen/final.txt:443:many of our nation's coastal ecosystems. They include algal blooms
```

__3. grep with -e__

Example 1:

Example 2:   
   
__4. grep with -l__

Example 1:

Example 2:   
