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
