Part 1 - Bugs
Choose one of the bugs from week 4's lab.

Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).

`   public void testReverseInPlace() {
        int[] input = {1, 2, 3};
        int[] expectedOutput = {3, 2, 1}; 
        ArrayExamples.reverseInPlace(input);
        assertArrayEquals(expectedOutput, input); 
    }
}`
An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown).

` public void testReverseInPlace() {
        int[] input = {1, 2, 3, 4};
        int[] expectedOutput = {4, 3, 2, 1}; 
        ArrayExamples.reverseInPlace(input); 
        assertArrayEquals(expectedOutput, input); 
    }`
The symptom, as the output of running the two tests above (provide it as a screenshot -- one test should pass, one test should fail).

<img width="994" alt="Screenshot 2024-05-08 at 10 58 38 PM" src="https://github.com/Diegoocse/CSE-15L---Lab-Report-3/assets/146890166/eba3f087-3020-4559-8309-3e160705f123">

The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown).
Briefly describe (2-3 sentences) why the fix addresses the issue.

Before: 

`static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }`

After:

`static void reverseInPlace(int[] arr) {
    int firstElement = arr[0];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
    arr[arr.length - 1] = firstElement;
  }`

The original code lacked a mechanism to preserve the first element of the array during the reversal process. In the after version, the first element is stored before the reversal loop and placed back at the end afterward, preventing the loss of original data caused by overwriting elements with their counterparts from the end in the original code. This allows for the element to be correctly reversed.

Part 2 - Researching Commands
Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose. To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works. Also consider asking ChatGPT!

1) I chose theg grep command and these aree some 4 intresting comand-line options
   - `grep -i "pattern" file.txt`
   - `grep -r "pattern" directory/`
   - `grep -v "pattern" file.txt`
   - `grep -c "pattern" file.txt`


For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

2)
Type command line argument:
  - First example: `find ./technical/ -type f`
    Output:
  -`./technical/file1.txt
    ./technical/Directory1/file2.txt
    ./technical/Directory2/file3.txt
    ./technical/emptyfile.txt`
  - Second example: `find ./technical/ -type d`
    Output:
  -`./technical/Directory1
    ./technical/Directory2
    ./technical/Directory3`
    
The type command line argument in find is used to filter files based on their type, such as regular files or directories, facilitating specific file-based operations or organizational tasks.

  Size command line argument:
    -First example: `find ./technical/ -type f -size +1M`
      Output:
    -`./technical/largefile1.txt
      ./technical/Directory1/largefile2.txt`
    - Second example: `find ./technical/ -type f -size -100k`
      Output:
    -`./technical/smallfile1.txt`
    The size argument in find filters files by size for efficient management. For instance, -size +1M identifies files larger than 1MB, and -size           100k finds files smaller than 100KB, aiding in managing different file sizes.


  Empty command line argument:
    -First Example: `find ./directory/ -type f -empty`
      Output:
      - `./directory/file1.txt
          ./directory/subdirectory/empty_file.txt`
    -Second example: `find ./directory/ -type d -empty`
      Output:
        -`./directory/empty_dir
          ./directory/subdirectory/another_empty_dir `
The empty argument in find locates empty files and directories, useful for decluttering and saving space. For instance, -type f -empty finds empty files, and -type d -empty locates empty directories, aiding in structure management and cleanup.

User command line argument:
      -First example` find /home/user1/ -user user1 `
        Output:` /home/user1/file1.txt
                  /home/user1/file2.txt`
      - Second Example` find /home/user2/ -not -user user1`
        Output:` /home/user2/file3.txt
                  /home/user2/file4.txt`
The user argument in find searches for files based on ownership. For example, -user user1 locates files owned by "user1," aiding in user-specific management. Conversely, -not -user user1 finds files not owned by a specific user, useful for access control or cleanup.

  



Along with each option/mode you show, cite your source for how you found out about it as a URL or a description of where you found it. See the syllabus on Academic Integrity and how to cite sources like ChatGPT for this class.

For the grep commands The prompt that I gave ChatGpt was "what are 4 different examples of comand-line arguments using grep?" the output that it have me were those 4 unique command-line options
