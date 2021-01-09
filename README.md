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
# I. Introduction
I have been using Unix Command Line for a while now and I can not stop talking about how usefull they are.  It saves me so much time not have to touch my mouse and get lost in my Finder.

Let's not watse time.

This tutorial is a collection of what I think are usefull linux commands that no matter how comfortable you are with your Mac, you still can use them.

This tutorial assumes you run the command lines in a Mac terminal.  
# II. So Why Unix Command Line 
it is so much faster.  It is quicker to write a couple letters or commands and click enter then just look through all menu options.

That single reason is good enough for us to learn them.
# III. Common Commands 
to start:
1. Lauch your terminal in Mac.
2. Create a working directory for this tutorial:
	please follow the steps for now, I will explain later.
	in your terminal, type:
	
    $mkdir unix_tutorial
    $cd unix_tutorial

## mkdir
stands for make directory
***mkdir [name_directory]***  create a directory names name_directory if it does not exist

## cd
stands for change directory. 
***cd [name_directory]*** changes the current working directory to name_directory

    $mkdir unix_tutorial   
    $cd unix_tutorial

what we did above were:

first: we create a directory name unix_tutorial

second: we change the working directory to unix_tutorial.

Yay!  We have set up our work space.
Up next, in your terminal, type: vm_stat

    unix_tutorial xingvoong$ vm_stat
   explanation:
   
   **unix_tutorial** is our working directory
   
   **xing_voong** is my user name on my personal laptop
   
   **$** the dollar sign is the start of a unix command
   
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

***vm_stat*** stands for virtual memory statistics.

***vm_stat*** display information about CPU memory and lock I/O

## echo $PATH

    unix_tutorial xingvoong$ echo $PATH
    ~/mongodb-macos-x86_64-enterprise-4.4.0/bin:/Users/xingvoong/.gem/ruby/2.6.0/bin:/usr/local/opt/ruby/bin:/usr/local/opt/ruby/bin:/Library/Frameworks/Python.framework/Versions/3.6/bin:/anaconda/bin:/bin:/sbin:Users/bin:/Users/local/sbin:/Users/local/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/VMware Fusion.app/Contents/Public:/opt/X11/bin

$PATH is a enviroment variable.

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

  
           

***cal -y*** shows the current year calandar

For each command in unix, there are many options.  Options are represented by dash **"-"**.

In the above command, ***-y*** mean choose the ***year*** option.


## man
To get more information and options for a command, use ***man***.
Exp:

    $ man vm_stat 
*to exit out terminal after using man command: control + Z*

## touch
create a file by touching it

    $ touch a_file.txt
   in your favorite editor, open a_file.txt, type "hello, this is a file I use to learn unix"
### ls
stands for list.  It lists all the files and directories in the current enviroment variable.

    $ ls
    a_file.txt
   there is only one file in our current working directory
## cat
 stands for concatenate.  It allows us to:
 1: view contain of a file
 
    $ cat a_file.txt
    hello, this is a file I use to learn unix.
   
   2: concatenate two files:
   
    $ touch file2.txt
   
   create a second file for concatenating
   in your editor, open file2.txt, type "this is a second file"
   to concatenate a_file and file2, do:
   
	$ cat a_file.txt file2.txt
      hello, this is a file I use to learn unix.
    this is a second fileXings-MacBook-Pro:unix_tutorial xingvoong$
  Since I did not have a new line at the end of file2.txt
  The outputs are not that pretty.
  Go back to file2.txt to add a new line. 
  
  To write the output to a new file, simply do:
  
    $ cat a_file.txt file2.txt > file3.txt
  the above command writes content of a_file.txt and file2.text into file3.text
  
    $ ls
    a_file.txt  file2.txt  file3.txt
 Now, there are three files in this directory.
 to view the content of file3.txt
 

    $ cat file3.txt
    hello, this is a file I use to learn unix.
    this is a second file
## who
displays users who recently logged into the computer

    unix_tutorial xingvoong$ who
    xingvoong console  Jan  9 13:28
    xingvoong ttys000  Jan  9 13:51
    xingvoong ttys001  Jan  9 21:48
yes, it was me the entire time.  Noone hack my computer.  I hope noone hack yours either
 
 to be continue ... 
