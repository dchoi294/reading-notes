# Practice in the Terminal

**The Command Line**,
or terminal, is "a text based interface to the system." Users are able to enter commands by typing them on the keyboard and feedback will be given to the user similarly as text. 
ex.
user@bash: ls -l /home/ryan
user@bash is a prompt, ls is a command, and the rest is argument.

**Basic Navigation**
pwd => Print Working Directory, shows user's current working directory.
ex.
user@bash: pwd
/home/DonChoi
ls => list, which shows user a list that is in the working directory.
ex.
user@bash: ls
bin Documents public_html

**More About Files**
Everything is a file, text file, directory, keyboard, monitor, etc. As such it is possible to have two or more files and directories with the same name but letters of different case. Spaces in file and directory names are perfectly valid but we need to be a little careful with them.

**Everything is a file under Linux**
Even directories.
**Linux is an extensionless system**
Files can have any extension they like or none at all.
**Linux is case sensitive**
Beware of silly typos.

**Manual Pages**
"The manual pages are a set of pages that explain every command available on your system including what they do, the specifics of how you run them and what command line arguments they accept. Some of them are a little hard to get your head around but they are fairly consistent in their structure so once you get the hang of it it's not too bad." 

man command  
Look up the manual page for a particular command.
man -k search term
Do a keyword search for all manual pages containing the given search term.
/term  
Within a manual page, perform a search for 'term'
n
After performing a search within a manual page, select the next found item.

**File Manipulation**
mkdir
Make Directory - ie. Create a directory.
rmdir
Remove Directory - ie. Delete a directory.
touch
Create a blank file.
cp
Copy - ie. Copy a file or directory.
mv
Move - ie. Move a file or directory (can also be used to rename).
rm
Remove - ie. Delete a file.
No undo
The Linux command line does not have an undo feature. Perform destructive actions carefully.
**Command line options**
Most commands have many useful command line options. Make sure you skim the man page for new commands so you are familiar with what they can do and what is available.
