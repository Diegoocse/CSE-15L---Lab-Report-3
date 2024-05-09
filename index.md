Part 1 - Bugs
Choose one of the bugs from week 4's lab.

Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).

An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown).

The symptom, as the output of running the two tests above (provide it as a screenshot -- one test should pass, one test should fail).

The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown).
Briefly describe (2-3 sentences) why the fix addresses the issue.


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

  Size command line argument:
    -First example: `find ./technical/ -type f -size +1M`
      Output:
    -`./technical/largefile1.txt
      ./technical/Directory1/largefile2.txt`
    - Second example: `find ./technical/ -type f -size -100k`
      Output:
    -`./technical/smallfile1.txt`

  Empty command line argument:
    -First Example: `find ./directory/ -type f -empty`
      Output:
      - `./directory/file1.txt
          ./directory/subdirectory/empty_file.txt`
    -Second example: `find ./directory/ -type d -empty`
      Output:
        -`./directory/empty_dir
          ./directory/subdirectory/another_empty_dir `

    User command line argument:
      -First example` find /home/user1/ -user user1 `
        Output:` /home/user1/file1.txt
                  /home/user1/file2.txt`
      -
      -Second Example` find /home/user2/ -not -user user1`
        Output:` /home/user2/file3.txt
                  /home/user2/file4.txt`
  





    






That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

Along with each option/mode you show, cite your source for how you found out about it as a URL or a description of where you found it. See the syllabus on Academic Integrity and how to cite sources like ChatGPT for this class.
