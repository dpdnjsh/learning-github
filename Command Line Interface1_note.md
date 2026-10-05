# Command Line Interface

### Shell comand
---
- pwd: shows the current path in a hierarchical directory
- cd: change directory  
  `cd (directory name)`
- ls: list files in the working directory

  ```
  / root  
  . current directory  
  .. upper-level directory  
  ~ home of current user
  /[directory name]: absolute path
  ./[directory name]: relative path
  ../[directory name]: relative path
  ```
  ***Example***
  ```
  $ cd ../ -> 현재 위치의 상위 폴더로 이동
  $ cd ../oss/folder1 -> 현재 위치의 상위 폴더로 이동한 후 oss 폴더의 foder1으로 이동
  ```
- -l: show detailed information(long format)
- -h: size in units (with -l)
- -a: show all files including hidden files (names starting with '.')  
  includes '.' (current directory) and '..' (parent directory)
- -la: -l + -a (same as -al)

| command | result |
| ------ | ------ |
| ls /[directory name] | list the files in the specified directory |
| ls -l | list the files in the working directory in long format |
| ls -l /etc /bin | list the files in the /bin directory and the /etc directory in long format |
| ls -la .. | list all files in the parent of the working directory in long format |

- clear: clear the terminal screen (same as Ctrl + L; history is not cleared)
  - 'up arrow' key: show the previous command from history
  -  'down arrow' key: show the next command
- history: show the list of previously executed commands
- 'Tab' key: auto-complete file and command names

### Manipulation
---
- cp: copy files and directories
  - -i: interactive, ask for confirmation before overwriting an existing file
  - -R: recursive, copy directories and everything inside them

| command | result |
| ------ | ------ |
| cp file1 file2 | copy the contents of file1 into file2 (overwrites file2 if it exists) |
| cp -i file1 file2 | same as above, but asks for confirmation before overwriting (interactive) |
| cp file1 dir1 | copy file1 into the directory dir1 |
| cp -R dir1 dir2 | copy the directory dir1 and everything inside it (recursive) |
  
- mv: move files and directories or rename them

| command | result |
| ------ | ------ |
| mv file1 file2 | rename file1 to file2 if file2 doesn't exist; replace its contents with file1 |
| mv -i file1 file2 | same as above, but ask for confirmation before overwriting file2 |
| mv file1 file2 dir1 | move file1 and file2 into the directory dir1 |
| mv dir1 dir2 | rename dir1 to dir2 if dir2 doesn't exist; if dir2 exists, move dir1 into dir2|

- rm: delete files and directories ***permantely and irreversevely***
  - ***Warning: no undo (files are not moved to the trash)***
- rmdir: remove an empty directory ('rm dir1' (without -R) gives an error)

| command | result |
| ------ | ------ |
| rm file1 file2 | delete file1 and file2 |
| rm -i file1 file2 | same as above, but ask for confirmation before deleting each one |
| rm -R dir1 dir2 | delete the directories dir1 and dir2 and everything inside them |

- mkdir: make a new directory
- wildcard: special characters that match filenames
  - '*': zero or more characters
  - '?': exactly one character
 
| pattern | result |
| ------ | ------ |
| '*' | all filenames |
| 'g*' | all filenames that begin with the character "g" |
|' b*.txt' | all filenames that begin with the character "b" and end with the characters ".txt" |
| 'Data???' | any filename that begins with the characters "Data" followed by exactly 3 more characters |

  
### Help command
---
- man: show the manual page of a command
- help: show help for shell built-in commands
- --help: show a short usage summary of a command

### Exiting terminal
---
- exit: close the current terminal session (same as Ctrl + D)
