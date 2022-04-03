# Scripting-Notes
This repository will provide the notes I have taken regarding the scripting course (CSC498X) regarding the bash part of the exam. These notes are not perfect and are of course not complete but I'm trying my best lol! Enjoy!

# GUI

Graphical User Interface (GUI) have become a mean of interacting with a computer. They allow users to manipulate and control their files, programs and computer overall. It has increased the friendliness of a computer however these improvements have led to disadvantages mainly felt by scientists (us lol!)

These disadvantages include: repetition of operations, programs do not keep log of commands issued by gui, GUIs are not useful for controlling analyses on a cluster and finally guis take time and effort to develop and they mostly work on their intended OS.

However, we cans till manipulate a computer using *the shell*

# The Shell

The shell is a powerful that allows interacting with a computer through written instructions on the command line. It is entirely text based and requires acquiring a new set of skills; however, it will give access to a huge advantage for the long run when it comes to data manipulation and analysis skills.

# Scripting in Bash

The bash shell is he default shell in all major unix and linux distributions. You are required to learn bash scripting if you are working on any Unix-Based system. It is all about combining available programs in a clever and useful way

The shell can be accesed by a Linux System, a Linux virtual machine or disc image, or a shell emulator installed on your machine. Shells are customizable and powerful tools. They can perform a lot of tasks in simple commands or short scripts. But becareful as they can also delete, remove and alter data without any prior warning if you were to do any typo or misspell a file.

# Unix Shells

-sh
-bash
-csh
-tcsh
-ksh
-zsh

Windows offers the PowerShell or any unix shell via Cygwin

You can change shells. To know which shell you are using you can use cat /etc/shells or echo $SHELL

To change shells just call: chsh -s and specify which shell you want...

# UNIX

Unix is an old operating system developed by Bell Labs. It follows the philosophy "Write program that do one thing and do it well"

# Unix File System

The unix file system is a hierarchy of folders and files on the computer. It is arranged of a hierarchal structure. The root directory is the holder of all other files and folders. It is the most inclusive and has access to all directories. As for the Home Folder it is the personal account for each user. Each user has their own account on the computer and has their own home directory. When working on the command line, your view of the filesystem is based on the directory you are currently in.


![Screenshot (413)](https://user-images.githubusercontent.com/95071049/160133096-283457a5-1480-4a09-b3bc-cb3d36464b80.png)

# The Path

It is the written description of where something is located. It is usually a list of directories seperated by a slash. We have two kinds:

-Absolute: the complete description of the location of file in relation with the root

-Relative: description of the location of a file with respect to another file

The working dierctory is the directory you are currently in or located

# UNIX Utilities:

ls (list): lists or prints the files in a certain directory (if no directory is stated it lists the one in the working directory)

cd (change directory): change directory or move to another directory 

tilda (~): alias for the home directory 

cd ../: moves backward in directory structure

pwd: prints working directory

mkdir: make directory; rmdir: removes directory; cp: copy files; mv:move/rename a file/directory; rm: remove files 

Altering of data is done without warning. Removal is irreversible and can be removed/replaced/altered without warning (clobbered).

TAB: autocomplete; UP-Arrow: retrieves previour command; history to see the history of commands; Ctrl+R reverse search: searched the end of previous commands ( the end of the string and not the beginning

mkdir -p dir1/dir2: create dir1 and dir2 inside dir1

rmdir: will not remove a directory if it is not empty. You can use rmdir -r to remove a directory recursively (removes files inside a directory then removes the directory)

ls: -l (shows properties); -a (hidden files [file names starting with a dot .]; -t to sort by time (newest 1st); -r to reverse the order of sorting
![Screenshot (415)](https://user-images.githubusercontent.com/95071049/160144498-5b5caaab-d013-4012-8f90-7c7b1a9b1200.png)

chmod: change mod; chmod [option] <filename>...chmod u+x file; adds executable permission to users; chmod o-x file; takes executable right from others              
![Screenshot (417)](https://user-images.githubusercontent.com/95071049/160144997-3deee9af-f886-4347-adf9-ada59204cdfa.png)

less: a file program to show contents of a file
less file.txt;
more: similar to less but not memory efficient (more file.txt)

man -K keyword: search manual using a keyword (not necessarily an actuall bash command)
 
cp src.txt dest: copy src to dest
 
cp src1.txt src2.txt src3.txt dest: scr1,2&3 will be copied to dest

# Wildcards in Bash:
 
*: 0 or more occurences of any character; ?: a single occurence; [CHARACTED CLASS] ex: [abc] is either a or b or c. The asterisk stops at the path divider

# Handling text in the Shell

Processing large files: less text editor. Similarly we have move, nano, emacs, vi...use them as commands ex: less text.txt
  
Redirecting flow of data: to redirect the output of a program to a file rather than a screen, use > This makes it more flexible to extract and combine data. You can also use cat to concatenate. It takes a list of file names seperated by spaces and outputs the content of the files on the screen. Cat is useful for small files, it will dump th econtent of the files onto the terminal and ctrl+c will kill it if necessary
  
\> will overwrite the content of your file. however u can use >> to append the content to the end of the file so no previously existing data is overwritten and the new data is displayed at the end of the file.

cat *.txt > combine.txt will dump the content of all txt files into the combine.txt file

grep is a powerful command to search files for a specific pattern. It can be extended using the -E option and support regex.
  
![Screenshot (419)](https://user-images.githubusercontent.com/95071049/160158360-e86c9edf-589b-4e32-86bf-aa18c1a6c4ed.png)
  
# REGEX
  
![Screenshot (421)](https://user-images.githubusercontent.com/95071049/160158868-a51d9592-28c2-4eb5-9e2b-5308c8725a8f.png)

 # MORE ON GREP
 
 the -A NUM option: will display NUM lines after the match. grep -A 2 "match" file will find the match print it and print the two lines after the match
 
 -B NUM: same as -A but it will print the NUM lines before the match. grep -B 2 "match" file will find the match print it, print the two lines before the match and then it will print the match
 
-C NUM: is the combination of -A and -B. it will print NUM lines before the match, the match and NUM lines after the match
 
 -E: extended mode that supports regex 
 
 \> and >> redirect output to file but if we want to redirect output of one command so it becomes the input of another command we use the pipe or "|"
 
 history|grep ls will retreive all commands used in the terminal and grep ls will search only for the ls command which should display the correct the times we used ls
 
 ![Screenshot (424)](https://user-images.githubusercontent.com/95071049/160238100-c29263d4-1da1-479c-ae40-dc34fd8237b5.png)

 # Web Content
 
 To retreive web content or content fron an html document we can either use curl followed by the url or lynx. lynx isn't available on all machines and curl is more universal

we can redirect the content of curl to a file using >>
if we have URL1, URL2, URL3, URL4, URL5
 we can use regex. curl "URL[1-5]" >>URLOUTPUT.txt
 
we can use -o as well to create multiple files and store the content of a url in it
 
curl "URL[1-5]" -o output_#1.txt
 this will creat 5 output files called output1,2,3,4,5 and store each url in its respectie output file
 
 wget is used to download online content. wgets works with slow internet and incase of network failure it will keep retrying until it has downloaded the whole file.

wget http://website.com/files/file.zip will download the file.zip specified by the URL
 
# Scripts
 
A script is a text file containing shell commands that can be executed. The commands run in sequence. For a text file to be recognized as a script some things must be done first. You need to specify the path that the script file exists in to be able to execute it. You can add the file into the usr/bin or /bin directory and execute it from there but it is not advised since these directories can contain system programs. Naming errors and altering this data can be dangerous not to mention that you require administrative privileges. It is better to make a custom directory and inform the shell where to look for it.
 
 The directory of your shell is stored in reserved variable called $PATH. If you wish to add the custome directory you have to edit the .bash_profile.
 
 You can also turn on a warning signal for rm or cp by using set -o noclobber. but this is temporary only for the specific terminal session
 
 You can also turn the script into an executad by:

 >Adding the executable privelage
 
 >using the bash command (bash scriptFile.sh)
 
 >use the .sh extension when creating your file
 
 >Add the shebang to the beginning of the file: "#!"
 
 
 
# Alias
 
 If you want to save a long command, you can use an alias
 alias shortcut="longer command"
 
 ex: alias cx="chmod u+x"
 
 now I can simply type cx fileName and add the executable permission to the file for user groups
 This is temporary for the terminal session
 
 
# Head & Tail
 
head and tail are two commands used to display the first few lines (head) and the last few lines (tail) of a text file. By default the select the first 10 (head) and last 10 (tail)
 
If you use the -n option you can manipulate to display the first 5:
 
head -n 5 file.txt: this will diplay the first 5 lines of file.txt

head -n -5 file.txt: this will display everything except the last 5 lines

![Screenshot (428)](https://user-images.githubusercontent.com/95071049/160242889-d4cfafe9-6bd7-498d-b99c-f0caf09f00a2.png)

tail -n +5 file.txt: this will display lines starting from line 5
 
![Screenshot (426)](https://user-images.githubusercontent.com/95071049/160242942-312b1cb0-b9e9-4f06-891e-05f06b0d1669.png)

 To display the lines 8-10: $ head -n 10 test.txt | tail -n 3
 
 To display the lines 3-10: $ head -n -10 test.txt | tail -n +3
 
![Screenshot (431)](https://user-images.githubusercontent.com/95071049/160243112-97147324-659b-4147-9f58-608635ee490d.png)
 

# Word Count:
 
You can use the wc command to count words

wc filename will return:
 
a b c filename (a b and c being integers)

a: Represents the total number of lines in the file.

b: Represents the total number of words in the file
 
c: Represents the total number of bytes in the file. This is the actual size of the file
 
filename is just the name of the file 
 
# Cut
 
to extract vertical columns from a file
 
cut -f 1,3: returns column 1 and 3

cut -f 1,3: returns from column 1 to 3
 
cut -c 3-8: returns characts from 3 till 8

cut -f 5,9 -d ",": adds the , as the dilimiter
 
# Sort
 
sort is a simple and powerful command to rearrange lines in a text file. They are sorted numerically and alphabatically. The rules are as follows:
 
>> Lines starting with a number will appear before lines starting
with a letter.

>> Lines starting with a letter that appears earlier in the alphabet
will appear before lines starting with a letter that appears
later in the alphabet.
 
>> Lines starting with an uppercase letter will appear before lines
starting with the same letter in lowercase.

By default, the sorting starts with the first character in the line and the first column of the data 
 
 ![Screenshot (435)](https://user-images.githubusercontent.com/95071049/160249193-0e0c4e75-c3a3-48cc-86ec-5bd28355d904.png)

 
 ![Screenshot (434)](https://user-images.githubusercontent.com/95071049/160249202-f05eb5cf-8edf-4019-b3ad-ed3f74fce8f9.png)

# uniq
 
uniq will remove duplicates from the file and only keep a unique representation of the line. uniq best works with sort sincethe file must be sorted and duplicate entries must be adjacent
 
# sed
 
short for stream editor. It can be used to manipulate an input stream either from a file or a pipe line |
sed 's/REGEXP/REPLACEMENT/FLAGS' filename
 
s-> search function

REGEXP->THe pattern or regular expression sed is looking for
 
REPLACEMENT->what we want to replace our text with
 
FLAGS->we have 'g' (replaces every instance...without it only one instance is changed) and 'i' (case-insensitive). We can specify a number n as a flag to replace the nth occurence of a word
 
You can also add a preceeding pattern. So if I want to search and replace a certain line but that line has to also have a diffenerent pattern...for example

Consider this as input.txt:

Instruction Guides
1. Linux Sysadmin, Linux Scripting etc.
2. Databases - Oracle, mySQL etc.
3. Security (Firewall, Network, Online Security etc)
4. Storage in Linux
5. Productivity (Too many technologies to explore, not much time available)
Addition FAQS
6. Windows- Sysadmin, reboot etc.
 
sed '/Sys/s/Linux/Unix/g' input.txt will replace the word Linux with Unix only for lines with the word Sys
 
sed '/\-/s/\-.*//g' input.txt will use regexp to find linex containing a - and remove that dash and everything after it
 
Instruction Guides
1. Linux Sysadmin, Linux Scripting etc.
2. Databases 
3. Security (Firewall, Network, Online Security etc)
4. Storage in Linux
5. Productivity (Too many technologies to explore, not much time available)
Addition FAQS
6. Windows
 
 sed 's/...$//'input.txt will remove the last three characters
 
Instruction Gui
1. Linux Sysadmin, Linux Scripting e
2. Databases - Oracle, mySQL e
3. Security (Firewall, Network, Online Security e
4. Storage in Li
5. Productivity (Too many technologies to explore, not much time availab
Addition F
6. Windows- Sysadmin, reboot e
 
we seperate commands using a semi-column (;)

sed 's/^#.*//;/^$/d' input.txt will replace all lines witha # to blank lines and the command after the ; will remove those blank linkes
 
# AWK
 
awk is a programming language within the shell used to manipulate structured data and generate reports. It read the file, searches for a pattern, performs a task for the matched lines and returns nothing if no pattern is found.
 
input.txt:
100 Thomas 	 Manager 	 Sales 		    $5000
200 Jason 	  Developer Technology 	$5,500
300 Sanjay 	 Sysadmin 	Technology 	$7,000
400 Nisha 	  Manager 	 Marketing 	 $9,500
500 Randy 	  DBA 		    Technology 	$6,000
awk '{print $2,$5}' input.txt will print the 2nd and 5th row (employee name and salary)
Thomas $5000
Jason $5,500
Sanjay $7,000
Nisha $9,500
Randy $6,000
each word in a line is stored in a variable. $1 is the 1st word, $2 is the 2nd and so on. $0 represents the whole line and NF represents the total number of fields in a record
 
# find
 
the find command takes a path and searches for files in a certain pattern
find path patter: searches for files that match the pattern
 
find /etc -name "*mail*" searches for files with the word mail in their name
 
find / -type f -size +100M searches for files with size greater than 100M

find . -mtime -2 finds files that have been modified in the last two days

# xargs
 
Useful if you want to execute a command on input from stdin or derived input. it is very useful if you want the command to run on multiple files. 
 
# Process
 
Every time you call a command you envoke a process. The OS keeps track of these processes using a 5 digit pattern called a PID. 
We have foreground and background processes. Foreground occur when we issue any command. The terminal cannot be used until the command is done. This can be time consuming. To make it run in the background it is enough to add an ampersand to the end of the command.
You can list processes using the ps command and stop them using CTRL+C or kill -9 PID


