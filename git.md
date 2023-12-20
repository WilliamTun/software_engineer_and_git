Commit structure

- Commit:
  contains metadata: author, commit message, timestamps
  each commit has a unique 40 character string called a HASH identifier.
  HASH identifer created via a hash function
  which is essentially a pseudo-character generator
- Tree:
  tracks and locations of repo
- Blob:
  binary large object - store of files & data
  compressed snapshot of contents of file when commit happened


===== Commands for summarising commits
- git log:
  shows history of all commits, and the metadata of each commit (timestamp+author)
  press "spacebar", to navigate information
  press "q", to return to the terminal
- git show <first 6-8 characters of hash id>
  git show c27fa856
  shows specific commit
  and the metadata log
  and the changes the commit made to previous head

===== Commands for summarising changes to files
- git diff -r HEAD     # compare to most recent commit
  git diff -r HEAD~1   # compare to second most recent commit
  git diff -r HEAD~2   # compare to third most recent commit
  compare staged files to the last commit
- git diff <hashid_1> <hashid_2>  # compare two specific commits
  git diff HEAD~3 HEAD~2          # compare x last commit with y last commit
 
- git annotate <filename>     # shows changes in document by line
                              # outputs: hash, author, timestamp, line number, line content


===== Commands for undoing mistakes before commit
- git reset HEAD           # unstage all files
- git checkout -- <file>   # undo your changes to a file and lost your changes forever
- git checkout .           # undo all changes to all files + lost edits forever
- git checkout <hash_id> <file> # revert file to version from specific commit + lose current edits forever



===== Commands to investigate file history
git log -3                                                # restrict number of commits displayed
git log -3 <filename>                                     # look at commit history (up to 3) of one specific file
git log --since='Month Day Year'                          # look at commit history by date
git log --since='Month Day Year' --until=<Month Day Year> # look at commit history by date




===================================================================================
===================================================================================
===================================================================================


======= Git configurations

git config --list     # shows local user.name, user.email, repo metadata etc

There are 3 levels of settings:
1. local
2. global
3. system

# change a configuration
git config --global <setting> <value>
git config --global user.email willtun1991@gmail.com # change email
git config --global user.name 'Will Tun'             # change username




===================================================================================
===================================================================================
===================================================================================

=========== Git branches

# compare differences between two branches
git diff <branch1> <branch2>


# handling conflicts
- prevention of conflicts is better than cure of conflices
- tip: use each branch for a specific task
       to reduce risk of conflicts
- tip: avoid editing the same file from multiple branches

 



===================================================================================
===================================================================================
===================================================================================


====== Git repo maintenance

tip: avoid nested repos - having a git repo in another git repo
     as this will create two or more .git directories