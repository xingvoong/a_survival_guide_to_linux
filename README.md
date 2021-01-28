sources and references:\
1: LINUX®ESSENTIALS, Second Edition by Christine Bresnahan and Richard Blum

2: CS160A, City College of San Francisco 

3: https://linuxhint.com/bash_wildcard_tutorial/

4: my own experiences

Table of Contents:

[I. Introduction](#i-introduction) 

[II. So Why Unix Command Line](#ii-so-why-unix-command-line) 

[III. Common Commands](#iii-common-commands)
	

 1. [mkdir](#mkdir)
 2. [cd](#cd)
 3. [vm_stat](#vm_stat)
 4. [echo $PATH](#echo-path)
 5. [cal -y](#cal--y)
 6. [man](#man)
 7. [touch](#touch)
 8. [ls](#ls)
 9. [cat](#cat)
 10. [who](#who)
 11. [rm](#rm)
 12. [cp](#cp)
 13. [mv](#mv)
 14. [wildcard](#wildcard)
 15. [wc](#wc)
 16. [receiving and writing information](#receiving-and-writing-information)
 17. [multiple commands in one line](#multiple-commands-in-one-line)
 18. [sort](#sort)
 19. [echo](#echo)
 20. [cut](#cut)
 
# I. Introduction
I have been using Unix Command Line for a while now and I can not stop talking about how useful they are.  It saves me so much time not have to touch my mouse and get lost in my Finder.

Let's not watse time.

This tutorial is a collection of what I think are useful linux commands that no matter how comfortable you are with your Mac, you still can use them.

This tutorial assumes you run the command lines in a Mac terminal.  
# II. So Why Unix Command Line 
it is so much faster.  It is quicker to write a couple letters or commands and click enter then just look through all menu options.

That single reason is good enough for us to learn them.
# III. Common Commands 
to start:
1. Launch your terminal in Mac.
2. Create a working directory for this tutorial:
	please follow the steps for now, I will explain later. \
	In your terminal, type:
	
    $mkdir unix_tutorial
    \
    $cd unix_tutorial

## mkdir
stands for make directory \
***mkdir [name_directory]***  create a directory names name_directory if it does not exist

## cd
stands for change directory. \
***cd [name_directory]*** changes the current working directory to name_directory

    $mkdir unix_tutorial   
    $cd unix_tutorial

what we did above were:
first: we create a directory name unix_tutorial \
second: we change the working directory to unix_tutorial. \
Some extra tips on `cd` command \
to go back to the previous directory, do:

    $ cd ..
to go back to the home directory, do:

    $ cd ~

Yay!  We have set up our work space.
Up next, in your terminal, type: vm_stat

    unix_tutorial xingvoong$ vm_stat
   explanation:
   **unix_tutorial** is our working directory\
   **xing_voong** is my user name on my personal laptop\
   **$** the dollar sign is the start of a unix command \
   **vm_stat** is a unix command 

## vm_stat
    Mach Virtual Memory Statistics: (page size of 4096 bytes)
    Pages free:                               41457.
    Pages active:                           1746982.
    Pages inactive:                         1736050.
    Pages speculative:                         9597.
    Pages throttled:                              0.
    Pages wired down:                        509005.
    Pages purgeable:                         102050.
    "Translation faults":                  85023185.
    Pages copy-on-write:                    3372555.
    Pages zero filled:                     47523657.
    Pages reactivated:                      1451823.
    Pages purged:                            822338.
    File-backed pages:                       623825.
    Anonymous pages:                        2868804.
    Pages stored in compressor:              379743.
    Pages occupied by compressor:            151040.
    Decompressions:                          189312.
    Compressions:                            969158.
    Pageins:                                2166764.
    Pageouts:                                 25776.
    Swapins:                                   2560.
    Swapouts:                                  2560.

***vm_stat*** stands for virtual memory statistics. \
***vm_stat*** display information about CPU memory and lock I/O

## echo $PATH

    unix_tutorial xingvoong$ echo $PATH
    ~/mongodb-macos-x86_64-enterprise-4.4.0/bin:/Users/xingvoong/.gem/ruby/2.6.0/bin:/usr/local/opt/ruby/bin:/usr/local/opt/ruby/bin:/Library/Frameworks/Python.framework/Versions/3.6/bin:/anaconda/bin:/bin:/sbin:Users/bin:/Users/local/sbin:/Users/local/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/VMware Fusion.app/Contents/Public:/opt/X11/bin

$PATH is an environment variable.
echo $PATH displays the enviroment variable that you are currently on.

## cal -y

    unix_tutorial xingvoong$ cal -y
                              2021
                              ...
        April                  May                   June          
    Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
                 1  2  3                     1         1  2  3  4  5  
     4  5  6  7  8  9 10   2  3  4  5  6  7  8   6  7  8  9 10 11 12  
    11 12 13 14 15 16 17   9 10 11 12 13 14 15  13 14 15 16 17 18 19  
    18 19 20 21 22 23 24  16 17 18 19 20 21 22  20 21 22 23 24 25 26  
    25 26 27 28 29 30     23 24 25 26 27 28 29  27 28 29 30           
                          30 31 
                              ... 

  
           

***cal -y*** shows the current year calendar
For each command in unix, there are many options.  Options are represented by dash a **"-"**.
In the above command, ***-y*** mean to choose the ***year*** option.

## man
To get more information and options for a command, use ***man***.\
Exp:

    $ man vm_stat 
*to exit out terminal after using man command: control + Z*

## touch
create a file by touching it

    $ touch a_file.txt
 
 or we can create a file using:

    > a_file.txt

explanation: the command means that an arrow points to a_file.txt.  If a_file.txt already existed, `> a_file.txt` will clear all the content in it.

   in your favorite editor, open a_file.txt, type:
   "hello, this is a file I use to learn unix"
### ls
stands for list.  It lists all the files and directories in the current environment variable.

    $ ls
    a_file.txt
   there is only one file in our current working directory
## cat
 stands for concatenate.  It allows us to:
 1: view content of a file
 
    $ cat a_file.txt
    hello, this is a file I use to learn unix.
the downside of this cat command is when a file contains so much content, there would be too much to display.
To overcome that, we could use

    $ more a_file.txt

   
   2: concatenate two files:
   
    $ touch file2.txt
   
   create a second file for concatenating \
   in your editor, open file2.txt, type "this is a second file" \
   to concatenate a_file and file2, do:
   
	$ cat a_file.txt file2.txt
      hello, this is a file I use to learn unix.
    this is a second fileXings-MacBook-Pro:unix_tutorial xingvoong$
  Since I did not have a new line at the end of file2.txt
  The outputs are not that pretty.
  Go back to file2.txt to add a new line. 
  
  To write the output to a new file, simply do:
  
    $ cat a_file.txt file2.txt > file3.txt
  the above command writes the content of a_file.txt and file2.text into file3.text
  
    $ ls
    a_file.txt  file2.txt  file3.txt
 Now, there are three files in this directory.
 To view the content of file3.txt
 

    $ cat file3.txt
    hello, this is a file I use to learn unix.
    this is a second file
## who
displays users who recently logged into the computer

    unix_tutorial xingvoong$ who
    xingvoong console  Jan  9 13:28
    xingvoong ttys000  Jan  9 13:51
    xingvoong ttys001  Jan  9 21:48
yes, it was me the entire time. Noone hacks my computer. I hope no one hacks yours either

## rm
to remove a file
create some files to remove

    $ touch a
    $ touch b
    $ touch c
  Now, we will remove them:
  

    $ rm a
remove file a from the current directory

    $ rm b c
remove file a and file b from the current directory

create a directory to remove

    $ mkdir to_remove
    $ rm to_remove
    rm: to_remove: is a directory
since to_remove is a directory, we can not remove it using to rm.
To remove a directory and files in that directory, we do:

    $ rm -r to_remove
`-r` means recursive

Now, our working directory look likes this:

    unix_tutorial xingvoong$ ls
    a_file.txt  file2.txt  file3.txt
## cp
copy file_a to file_b
create file_a.txt with content: "this is file a" \
create file_b.txt with content "this is file b"

    $ cp file_a.txt file_b.txt
    $ cat file_b.txt
    this is file a
Now, the content in file a is also the content in file b

## mv
mv file_a to file_b \
first, change the content in file_b.txt back to "this is file b"

    $ mv file_a.txt file_b.txt
    $ ls
    a_file.txt  file2.txt  file3.txt  file_b.txt
   After moving file_a.txt to file_b.txt, file_a.txt is deleted

    $ mv file_b.txt c.txt
    $ ls
    a_file.txt  c.txt  file2.txt  file3.txt
  After moving file_b.txt to c.txt, file_b.txt is deleted and file c.txt is created

## wildcard 

*this section along deserves it whole stands along tutorial.*

Usage:
- define a pattern for searching
- group multi files and directories

There are three main wildcard characters:
- star *
	- searches for a specific character one or more time
- square bracket []
	- acts similarly to a list argument in python, 
	- search for a range or a group of character in the bracket.
- question mark ?
	- finds fixed number of character where the question mark will specifiy the number of character

**Example 1: star**

    $ ls f*
    $ file2.txt  file3.txt
   the command `ls f*`list all the files that start with f.  `f*` mean one or more f
  
  In the current directory, create some more files.
  
    $ touch a b c
    $ ls
    a  b  c.txt  file3.txt
    a_file.txt  c  file2.txt
  List all file with a given extensions, such as .txt
  
    $ ls *.txt
    a_file.txt  c.txt  file2.txt  file3.txt
  
  **Example 2: bracket**
  Lists all file that contains character within a to z

    $ ls [a-z]
    a  b  c
Lists all file that contains character within a to z and with any extension

    $ ls [a-z]*.*
    a_file.txt  c.txt  file2.txt  file3.txt
**Example 3: question mark**
I want to search for files with 1 character in name

    $ ls ?
    a  b  c
 Searches for files with 5 characters in name and end with .txt entension 
 

    $ ls ?????.txt
    file2.txt  file3.txt
 ## wc
 

    $ wc file3.txt
    2  15  64 file3.txt
   the command above displays 4 fields of information:
   1. number of line 
   2. number of words
   3. number of characters
   4. the name of the file
   
In fact, you can get an individual field by specifing an option.

    $ wc -l file3.txt
    2 file3.txt
    
    $ wc -w file3.txt
    15 file3.txt
    
    $ wc -c file3.txt
    64 file3.txt

## receiving and writing information

This part is about the commands and characters that we have already seen but now we combine them for different usages.

**receiving:**  a command line receives information, what does this mean?

    $ ls *.txt
    a_file.txt  c.txt  file2.txt  file3.txt


  In here, the information is the start character.
  What if I do not want to display the result of `$ ls *.txt` in my terminal but another file called output.txt?
  We can do:
  

    $ ls *.txt > output.txt
 
 the `>` character redirects the output of `ls *.txt` to output.txt
 
 Now if we list all the file, we can see that output.txt is created

    $ ls
    a  b  c.txt  file3.txt
    a_file.txt  c  file2.txt  output.txt
 Let's see what inside output.txt, we should expect that it contains the output of command line `ls`
 
    $ cat output.txt
    a_file.txt
    c.txt
    file2.txt
    file3.txt
  ## multiple commands in one line
   We can do multiple command in one line to save time or to achieve a result that one command line alone can not do.  Yes, we are increasing the level of complexity.
  
  

    $ mkdir mul; cd mul
In the above command,  we created a directory called mul.  Right after that, we change our current directory to mul.  Two commands are seperated by semi colon ";"

Now, we are in `mul` .  We want to get back to the previous directory aka `unix_tutorial` by simply do `$ cd ..`
In unix_tutorial directory do:

    $ ls | wc -l
    9 
Let's break it down, `ls` lists all the files and directories in the current working directory. `wc -l` counts that result.


  ## sort
  create a file name letters.txt with content:
  a \
  c \
  e \
  b \
  d 

    $ cat letters.txt
    a
    c
    e
    b
    d

to sort the content of letters.txt file, we can do

    $ sort letters.txt
    a
    b
    c
    d
    e
  
the sort commands will not change the content letters.txt.  So save the result, we can do something that we have seen above.

    sort letters.txt > sorted_letter.txt
to sort in descending order, we can do

    $ sort -r letters.txt
    e
    d
    c
    b
    a
   - r: reverse option
## echo
display in terminal the information that given to the command.

    $ echo hello
    hello
 ## cut
 

    $ ls | cut -c1
    a
    a
    b
    c
    c
    f
    f
    l
    m
    o
    s
As we always do, let's break it down.
`-c1` specifies column 1 option.  So the above command first list all the files and directories.  Then cut them by their first column.  In this case, the first column is the first letter of their names.

    echo "a,b"  | cut -d, -f2
    b
  `-d` indicates a delimiter.  In the above example, the delimiter is comma ", "
  `-f2` means field number 2
  to return field number 1, we do
 
    echo "a,b"  | cut -d, -f2
    a
