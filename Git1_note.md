# Git

### Version control
---
We need a systematic management system for version control and collaboration. -> Git

|| changes | snapshots |
| ------ | ------ | ------|
| what is stored | base version + the changes of each file | A snapshot of all files at each commit |
| unchanged files | nothing stored | stored as a link to the previous identical file |

| type | description |
| ------ | ------- |
| Local | version database lives only on your own computer |
| Centralized | one central VCS server holds the database; client check out files |
| Distribute(Git) | every computer has a full copy of the version database, in addition to the server |

| state | where | meaning |
| ------ | ------ | ------ |
| modified | working directory | file changed, not yet staged |
| staged | staging area | marked to go into the next commit |
| committed | .git directory | safely stored in the local database |

### first-time setup
---
Configurations are stared at three levels (each level overrides the previous one: system -> global -> lacal)

| level | option | scope | file |
| ------ | ------ | ------ | ------ |
| system | `--system` | all users and repositories on the system | `/etc/gitconfig` |
| global | `--global` | all repositories of the current user | `~/.config/git/config` |
| local | `--local` | current repository only | `.git/gitconfig` |

### Basic Workflow
---
- Initializing a repository: initializing a repository in an existing directory  
`$ git init`  
- Check status: checking repository status  
`$ git status`  
- Stage files: adding a new file to be staged
```
$ git add <file>  # one file
$ git add <file1> <file2>  #several files
$ git add . # all files in the current directory
```
- Unstage a file: the file stays in the working directory but returns to untracked.  
`$ git rm --cached <file>`  
- Ignore files  
`$ nano .gitignore  #write file names/patterns to ignore`  

pattern examples
```
# ignore all .a files
*.a (all .a files)

# but do track lib.a, even though you're ignoring .a files above
!lib.a (do not ignore lib.a)

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO (only the top-level TODO)

# ignore all files in any directory named build
build/ (any directory named build)

# ignore doc/notes.txt, bot not doc/server/arch.txt
doc/*.txt (.txt directly in doc/ only)

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf (.pdf in doc/ and all subdirectories)
```

- Commit: only staged changes are commited  
  After commiting, git status -> nothing to commit, working tree clean.  
 `commit -m "msg"`
- View history
`$ git log`
- Change the branch name:
  ```
  $ git branch # list branches
  $ git branch -m <old> <new>  # rename master -> main
  ```
