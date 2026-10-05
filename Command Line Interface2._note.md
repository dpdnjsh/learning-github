# Command Line Interface

### I/O Redirection
---
- default: standard output is the screen, standard input is from keyboard
- '>': redirect output to a file(creates the file, overwrites if it exists)
- '>>': appends output to the end of a file(creates the file if it doesn't exist)
- '<': redirect input from a file
- cat: display the content of a text file
- '>' and '<' can be mixed in a single line.

### Pipelines
---
- '|': feed the output of the previous command to the input of the next command

### Expansion
special characters expand their meaning when given to shell commands

| command | result |
| ------ | ------ |
| echo print out the text | print out the text |
| echo* | '*' expands to all file names in the current directory |
| echo~ | '~' expands to the home directory |

backslash: ignore the line change, to enter a long command in multiple lines

### Premissions
---
- Linux is a multi-user system.
- Files and directories have a permission assigned differently to owner/group/others.
- r: read, w: write, x: execute
- chmod: change permissions(use a 3-bit number: owner/group/others)

| permission | binary | number |
| ------ | ------ | ------ |
| rwx | 111 | 7 |
| rw- | 110 | 6 |
| r-x | 101 | 5 |
| r-- | 100 | 4 |

| value | meaning |
| ------ | ------ |
| 777 | (rwxrwxrwx) No restrictions, anybody may do anything |
| 755 | (rwxr-xr-x) owner may read, write, execute; others may read and execute |
| 700 | (rwx------) only the owner may read, write, execute(private programs) |
| 666 | (rw-rw-rw-) all users may read and write |
| 644 | (rw-r--r--) owner may read and write; others may only read |
| 600 | (rw-------) owner may read and write; others have no rights(private data files) |

### Superuser
---
- A supersuser has all system administation authority.
- Some commands need superuser's privilleges.
- sudo: if you are a superuser, put 'sudo' before the command

| command | result |
| ------ | ------ |
| sudo some_command | run some_command with superuser's privileges |
| sudo -i | start a superuser session (prompt changes to root) |
| exit | get out of a superuser session |

### Text Editors & Shell Script
---
- CLI-based: vi/vim(powerful, hard to learn), Emacs(huge, many features), nano(easy, recommended for beginners)
- GUI-based: gedit(GNOME, beginner level), kwrite(KDE, syntax highlighting)
- shell script: write with an editor, then run with sh  
  ` $ nano myscript.sh `
- *if there is a problem on nano(in Windows), edit the file in any other text editor(e.g., 메모장)

### History
---
- history: show the previous command history, or save it to a text file

### Download
---
- wget: download files from the internet directly to the active directory (if the same file name exists, it is saved as 'horse.jpg.1')
- curl: fetch, upload, and manage data over the Internet
  `curl [options] [URL]`
  - -o: save with the file name I choose
  - -O: save with the original file name of the URL
 
### Search
---
- grep(Global Regular Expression Print): search text within files  
  `grep "search_term" file.txt`: print the lines that contain "search_term"
- -i: case-insensitive search (finds "apple" and "Apple")
- -v: invert the match (lines *not* containing the search term)
- -n: display line numbers along with matching lines
- -r: recursive search (all files in a directory and its subdirectories)

```
.* any character (.) zero or more times (*)
\d any digit (0-9)
[abc] any single character within the brackets
^ the beginning of a line
$ the end of a line
```
