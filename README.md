# Terminal 101

- [OS History](https://eylenburg.github.io/os_familytree.htm)
- [1st Edition Unix Manual](https://www.bell-labs.com/usr/dmr/www/1stEdman.html) - November 3, 1971

## Shell

- `echo $SHELL` - to see current shell
- `chsh -s /bin/bash` - change shell to bash
- `chsh -s /bin/zsh` - change shell to zsh

_Restart terminal window to apply changes_

## Shortcuts

- clear : `cntrl + l`
- move to end of line : `cntrl + e`
- move to beginning of line : `cntrl + a`
- move one char forward : `cntrl + f`
- move one char backward : `cntrl + b`
- move one word forward: `option + right arrow`
- move one word backward: `option + left arrow`
- remove all text to end of line from cursor : `cntrl + k`
- remove all text to beginning of line from cursor : `cntrl + u`

# Commands

_Tab autocompletes names_

- `date` - current date
- `ncal` - calendar of month - vertical
- `cal` - calendar - horizontal
- `ncal <month> <year>` - specific cal
- `echo` : read out anything

## History of Commands

- `history` : will output all commands run
- `history | less` : pages to scroll through with man pages toggle /scroll keys
- `!<comman#fromhistory` : _!84_ will rerun the command that is given
- `cntrl + r` : search history type command : down arrow to escape
- `history -c` : clears history record

**Saves a file of history under home directory**

- `.bash_history` : can open with `nano` to view all scripts run

# Options

Generally written first in the command

- prefixed with `-`
- `date -u` : universal time

_example_

```
ncal -j
ncal -3
```

**Multiple Options**

_same meaning different syntax_

- `ncal -3 -h -j`
- `ncal -3h`

## Long form option

_Some commad options accept not all_

- prefixed with `--`

_same command_

- `date -u`
- `date --universal`

## Options with parameters

Requires an input to compute

- `ncal -A 5` : 5 months after current month
- `ncal -B 3` : 3 months before current month

# MAN Pages - Commands Manual

- `man <command>` : _man ncal_ : Show documentation on command passed to `man`
- `q` : to exit
- `space` : move one page at a time
- `b` : back one page
- `/<command>` `enter`: _/-w_ : find command

## Synopsis

- `[ ]` : is opitional
- `...` : can pass multiple too
- `source_file` : plain text with underline means required

## Type

- `type` : shows the type of command

4 types of commands

- an exectuable program, usually stored in /bin, /usr/bin, /usr/local/bin. Compiled binary files.
- a build in shell command (bash, zsh, etc)
- a shell function
- an alias

## Which

Shows where the command is located on device

- `which clear` : outputs _/usr/bin/clear_ physical location

# Help

- `help <command>`

Commands built into shell are not in `man` pages normally. Use _help_

# Root

- `/` : root directory
- `~` : home directory

# Naviagtion

- `cd`
- `pwd` : print working directory (path)
- `ls` : list

## ls Options

- `-a` : show all _hidden_ folders
- `-l` : long format of list of files
- `-h` : human readable size format
- `-S` : sort by file size largest first

- `ls <path>` : _ls /_ to look inside any directory from any working dir
  - `ls <directory>` : outputs all contents in directory

## cd

- `cd` : change directory
- `cd ~` : go to home directory

Passing an absolute path from any working directory will take you there

# Creating files and directories

- `touch` : create file (can prove multiple file names)
- `mkdir` : create directory

Can provdie absolute path `../fileORdirName`

Can provide touch a file name to update last updated time of file (also lol)

- `file <filename>` : tells you the file type

**Use " " qoutes to create a file name with spaces**
_But ideal to not use spaces in file or directory names_

**mkdir**

`-p`

- option `-p` will make parent directory also : example `mkdir -p Horses/Mare` or `mkdir Horses/Mare -p`

# Nano

`pico <filename>` : built in text editor

all commands at bottom start with control key

# Deleting, Copying, and Moving

## Deleting

- `rm` : deletes. Not in trash actully completely gone.

**Folders**

- `rm -d` or `rmdir` : deletes directories that are empty
- `rm -r` : delete recursively. Deletes all files and directories with a direcory.

List out interactivly as it deletes to approve each removal

- `-i`

## Moving

- `mv <source> <destination>`

Can provide multiple files with a destination of a directory.

- `mv <filename> ..` : can move back to previous dir

### Renaming

- `mv <fileORDirName> <fileORDirNameThatDoesNotexist>`

_You can also provide new file name for destination path and rename and move at the same time_

## Copying

- `cp` : copying, syntax is similar to moving

To copy nested directories have to provide option flag

- `cp -r` : recurrsive copying

# Working with files

- `cat <file>` : concatenate contents of files, print out. Can provide many files.
- `less <file>` : print out contents with iteractive view program, for large files with lots of content
- `tac <file>` : cat in reverse. prints out in reverse
- `rev <file>`: print out contents but reversing the order of the words
- `head <file>` : print first 10 lines of file (default is 10)
  - `head -n 5 <file>` : prints first 5 lines
  - `-<Int>` : dont need `-n` can just provide `int` and `-`
- `tail <file>` : last 10 lines of file
  - `-n`
  - `-f` : follow, cursor will wait to print out next line (good for logs)
- `wc`: can tell us how many lines are in a file (shows output in below order)
  1. lines `-l` : can specify only one output parameter
  2. words `-w`
  3. bytes
  4. `-m` : number of characters
- `sort` : prints out the contents of file, but shows each line in Alphabetical order
  - `-r` : reverse order of sort
  - `-n` : will sory by numerical order
  - `-u` : ignore duplicates ony show unique values

# Redirection

- **standard output** : send command output to any device or location
- **standard errors** : send output of errors from command to any where
- **standard input** : input to command from any location _(example: file)_

## Standard Output

- `>` : redirect standard output to specific file
  - Over-writes the data in that file
- `>>` : will append the data when redirecting output

**example**
_date > standard-output.txt_ prints to txt file in this dir
_ncal -3 > standard-output.txt_

can echo out anything and then output that to file
If file does not exist will create it
_example_ : `echo "This is my Test" > test.txt`

## Standard Input

1. `0>` : dont need to specify 0

Send any value to command via file etc

- `<` : redirect standard input from a specific file.

### Combining Input and Output

2. `1>` : dont need to specify 1

Must provide in order of Input to Output

- `cmd < (inputFile) > (outputFile)`
- `cmd < (inputFile) >> (outputFile)` : append

## Standard Errors

3. `2>` : dont need to specify 2

Redirect output of errors to a file or any location

- `2>` : redirect error output to any where
- `2>>` : redirect error output to any where and _Append_

_example_ `sort read3.txt 2> error`

## Combining with error

Newer syntax

- `ls &> output` send output and errors to same file
- `ls &>> output` : append

Output command should be provided before error output command

- `cat file.txt > newFile.txt 2>> error.log`

**Redirect Ouput and Error to same location**

_Shorthand_

- `ouput.txt 2>&1`

_example_ `cat dogs.txt > output.txt 2>&1`

# Piping

Connect two commands
Redirect output from one command to another
Redirect a stream from one program to another program
Can pass endless amounts of pipes

_example: `date | rev`_

## Piping and Redirecting

- `>` : connects a command to a file
- `|` : connects a command to another command

# tr

Translate and manipulate characters

- `<a>` : char to change
- `<b>` : what to change char to

Requires a standard input `cat file.txt | tr <a> <b>`

**Delete a single char**

- `<a>` : char to delete

- `cat file.txt | tr -d <a>`
- `cat file.txt | tr -d a-z` : will delete all lowercase letters
- `cat file.txt | tr -d [:alpha:]` : will delete all letters
  - `[:digit:]` : Numbers etc **Character classes**
  - `[:blank:]` : Blank spaces and Tabs

# tee

- `tee <filename>` : capture output from one command and pass to a second command input

_example: ` cat test.txt | tee new-test.txt | wc -l`_

# Expansion
