# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

* print working directory:`$ pwd`
* create directory: `$ mkdir [options] <file_path>/<directory_name>`
* delete directory: `$ rmdir [options] <file_path>/<directory_name>`
* create file with `touch` command: `$ touch [options] <file_name>`
* delete file: `$ rm [-i] <file_path>/<file_name>`
* rename file: `$ mv <original_path/original_name> <original_path/new_name>`
* list hidden files: `$ ls -a <path>`
* copy file from one directory to another: `$ cp [options] <source> <destination>`
* display manual/documentation page for a command: `$ man <command>` or `$ man -k <search_term>`
* search in a file for expressions: `$ egrep [options] <expression(s)_to_search_for> <file>`

---

### Q2.  List Files in Unix   

What do the following commands do:  
* `ls`      list all files in current directory, standard constraints
* `ls -a`   list all files, including hidden files
* `ls -l`   list all files with long listing
* `ls -lh`  list all files with long listing, with unit suffixes for file sizes
* `ls -lah` list all files, including hidden files, with long listings and unit suffixes for file size
* `ls -t`   list all files sorted by most recent time modified
* `ls -Glp` list all files with long listing, and colorized directory names followed by a `/`  character 

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

* `ls -r`  displays all files in reverse order. Ex: to display files ordered by most recently accessed: `$ ls -ur`
* `ls -R`  displays all subdirectories as well
* `ls -GF` flags filenames with colorized output
* `ls -S`  list files sorted by size
* `ls -1`  list all files with one output per line

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` is a tool for enacting an operation, action, or utility with a list of inputs. Example:  

`ls *.txt | xargs -n1 ./make_dated_copy.sh`  

The script `make_dated_copy.sh` makes a copy of an input file with the current date as a prefix to the input file name. In the example above, I find all the text files in the current directory and pipe the file names to the next part of the command. `xargs` accepts that list and sends the files, one at a time, to be operated on once (`-n1`) by the `make_dated_copy.sh` script. `xargs` will run the script on the input until it has exhaused the list.
