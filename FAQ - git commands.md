 - Common commands:
   1. `git clone [url]`
   2. `git checkout master`
   3. `git push origin <branch>`
   4. `git pull origin <branch>`
   5. `git fetch origin --prune #sync remote and remove untracked remote branch`
   6. `git branch -D branchName #remove local branch`
 
 - Q: [branch] How to create new branch and check to that branch?
 - A: `$ git checkout -b [name]`

 - Q: [branch] How to create remote branch(push local branch to remote)?
 - A: `$ git push origin [name]`

 - Q: [branch] How to check exist branches?
 - A: `local branch: $ git branch`
       `remote branch: $ git branch -r`

 - Q: [branch] How to check out a new branch which track remote branch?
 - A: `$ git checkout -b ${branch_name} remotes/origin/${branch_name}`

 - Q: [branch] How to find out which remote branch a local branch is tracking:
 - A: http://stackoverflow.com/questions/171550/find-out-which-remote-branch-a-local-branch-is-tracking
   - `$ git branch -vv`

 - Q: [commit] How to pull remote but ignoring local changes?
 - A: http://stackoverflow.com/questions/4157189/git-pull-while-ignoring-local-changes . 
   1. `$ git reset --hard`/`git reset --hard origin/<branch>` //ignore local change and track to remote branch
   2. `$ git clean -f`, remove untracked files, `-df` to remove untracked files and directories, and `-xdf` to remove untracked or ignored files or directories.
   3. $ git pull 

 - Q: [commit] How to cancal a local change
 - A: http://stackoverflow.com/questions/4850717/how-to-cancel-a-local-git-commit 
   - `git reset HEAD~1`
   - `git reset HEAD~2`
   - `git reset HEAD~`
   - `git reset HEAD^`

 - Q: [commit] How to revert a remote commit
 - A: `git revert <SHA-1>`
   - Rewind back to a specified commit: `git reset --hard <SHA-1>`
     - (Note that --hard would make you lose any non-committed changes in the working directory).
     - http://stackoverflow.com/questions/927358/how-to-undo-the-last-commit 
     - http://stackoverflow.com/questions/4114095/revert-to-a-previous-git-commit 

   - Git revert to a commit: http://stackoverflow.com/questions/1895059/revert-to-a-commit-by-a-sha-hash-in-git
     - `git stash`
     - `git reset <SHA-1>`
     - `git reset --soft HEAD@{1}`
     - `git commit -m "Revert to <SHA-1>"`
     - `git reset --hard`
     - `git stash pop`

 - Q: [commit] How to undo a commit and redo
 - A: http://stackoverflow.com/a/927386 
   - `$ git commit ...` (1)
   - `$ git reset --soft HEAD~1` (2)
   - << edit files as necessary >> (3)
   - `$ git add ....` (4)
   - `$ git commit -c ORIG_HEAD` (5)

 - Q: [commit] How to revert change on single file?
 - A: http://stackoverflow.com/questions/2733873/reverting-a-single-file-to-a-previous-version-in-git
   - `git log path/to/file # git log -p path/to/file`
   - `git checkout <commit> path/to/file`

 - Q: [commit] How to amending the most recent commit message:
 - A: `git commit --amend`


 - Q: [commit] How to show changes on commit:
 - A: http://stackoverflow.com/a/1157854 
   - `git show <commit hash>`

 - Q: [commit] How to revert the file to specified version
 - A: `git checkout <commit hash> <filename>`

 - Q: [commit] How to show change between local file and specific version?
 - A: `git diff <commit hash> <filename>`

 - Q: [commit] How to diff between local uncommitted changes and origin:
 - A: `git diff origin/{branch_name}`

 - Q: How to rebase local branch:
 - A: Steps: 
   1. `git fetch origin`
   2. `git rebase -i origin/master`
   3. `git rebase --continue`
   4. `git push -f origin ${origin_branch_name}`

 - Q: Git tag operations
 - A:
   - `$ git tag -l`
   - `$ git checkout tags/<tag_name>`
   - `$ git checkout tags/<tag_name> -b <tag_name>`

 - Q: How to update git remote url:
 - A: Steps: http://stackoverflow.com/questions/2003505/how-to-delete-a-git-branch-both-locally-and-remotely
   1. open command line tool, change directory to you project home
   2. input `git remote -v` to see currently url
   3. input following command to update the remote url: `git remote set-url origin ${new_remote_url}`
   4. re-input `git remote -v` to see currently url to check whether success

 - Q: git remote operation:
 - A:
   - http://stackoverflow.com/questions/19801455/git-removing-upstream-from-local-repository 
   - https://help.github.com/articles/removing-a-remote/ 
   - Older (backwards-compatible) syntax: `$ git remote rm upstream`
   - Newer syntax for newer git versions: `$ git remote remove upstream`




