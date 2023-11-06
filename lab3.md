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

Example 1: In this command, grep -e is used to specify to string patterns. The command simply returns every line  that contains "afford" or "non-profit." This is useful when wanting to search for multiple pattterns/strings simultaneously in a file with an output of just a text line. (current directory in example: /Users/sebastientello/Desktop/School/CSE 15L/lab5/docsearch-main/technical/government/media)

*Input*
```
grep -e "afford" -e "non-profit" Legal_Aid_in_Clay_County.txt
```

*Output*
```
often are the ones who can least afford it. That's when
office in Green Cove Springs, the non-profit agency handled more
resources they don't need shelter and they can afford private
```


Example 2: This command uses -v and -e to return the contents of the text file exculding the given string which in this case is "New York Law Journal." This can be useful when cleaning data, removing unwanted information in a file, or simplifying search results by excluding irrelevant data. (current directory in example: /Users/sebastientello/Desktop/School/CSE 15L/lab5/docsearch-main/technical/government/media)

*Input*
```
grep -v -e "New York Law Journal" Survey.txt
```

*Output*
```
Survey: Most Law Students Can't Afford Public Service

Thomas Adcock
12-09-2002
For those worried about the indebtedness of young attorneys --
and how this affects the future of government and public interest
law -- fresh anxiety arrived last month with a national survey
showing that two-thirds of today's law school graduates cannot
afford to think about taking low-paying jobs.
Mortgage-sized tuition debts, warned the report, have dire
consequences for the future of poverty law agencies and legal
departments in state and federal government. The 47-page report,
"From Paper Chase to Money Chase: Law School Debt Diverts Road to
Public Service," was sponsored by the Partnership for Public
Service, Equal Justice Works and the National Association for Law
Placement.
At the heart of the report was a survey of 1,622 third-year law...
```
 
__4. grep with -l__

Example 1: The command searches the given path for a string and returns all the texts files within that directory path with the string. This is useful when wanting to identify relevant files and find specific patterns in a folder with text files. 

*Input*
```
grep -l "conditions" ./technical/911report/*
```

*Output*
```
./technical/911report/chapter-1.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
```

Example 2:   
