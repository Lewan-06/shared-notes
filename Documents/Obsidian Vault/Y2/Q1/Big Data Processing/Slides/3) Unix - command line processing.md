  
Extract data -> tranform data -> load
Extract -> select -> process -> summarise -> plume -> program

  

 Basics: 
- a command followed by > puts the output of the command into a file
- Can combine programs by using the | symbol (pipeline)
- Making a command run in the background by adding & at the end of the command

  

To store a variable write the name of it followed by an =, then to call it you need to put a $ before it.

Single quotes make all special characters lose meaning (including variables), double quotes make all special chars lose meaning except variables.

  

Grouping commands:
- to sequentially run them use a ; between the commands
- If multiple commands separated by ; are put in brackets then both the contents are pushed into a file
- Adding $? Outputs the success of the last operation (0 for success, something else, usually 1 for failure)
- Command 1 || Command 2 => run command 1, if command 1 fails run command 2 
- Command 1 && Command 2 => run command 1, if command 1 success run command 2
- Other way is to use if statements

  

Loops: 
- while
Example:  
while
- for 
Example: 

  

**Fetching data** 
1) From a url (curl, wget)
2) From a database (mysql, psql, etc.)
3) From secure host (ssh)
4) From local file system (find -> {-name, -type f(file) or d(directory)})
Converting (ie. binary) file to text:
-nm, ldd, readily, dumpbin, javap
-ar, ldd
Compress/ Archive files together:
- tar, jar (for java)
- For windows : readlog, winner, docprop

  

**Filtering data**
- grep (we specify a regular expression and searches for it in a file and prints it)

Example:  
grep aa words => search for all words containing “aa”


**RegEx**:
. = any character; ^a = searching for stuff starting with “a”; a$ = searching all words ending in “a”; 

a* = the character “a” 0 or more times; [a-z] = searches for words containing the characters in the brackets; [^a-z] = searches for words not containing the characters inside the brackets; \ = makes the special character lose meaning; (a.b) = searching for the characters grouped together; + = 1 or more times; ? = 0 or 1 times; {8} = repeat 8 times, {, 8} = repeat up to 8 times

  

-awk (specify matched pattern and code inside {}, $ will specify field)