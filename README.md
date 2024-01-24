# Git&GitHub Workshop

Kamila: GitHub

Monika: Branches

Lilie: Conflicts

First, that's not really important, but Git doesn't actually record changes, but rather snapshots of our files (at least conceptually; it will use packfiles to store things efficiently and will actually store changes –diffs– in some cases), and will generate diffs on-demand. This sometimes shows in the result of some commands though (like why some commands show one file removed and another added, while other commands show a file being renamed).
- <a href="https://learngitbranching.js.org" target="_blank">Vizualizer</a>
- <a href="https://miro.com/welcomeonboard/ZFdFdXRNNXViZmlYcVpuSUwxbEJlVkhnNlVEa0hZVTY4UlhzelhSQTVqYlYxV1pYbzBna2UySndXMmxFem45NHwzNDU4NzY0NTc1NzUxNTA0Njc5fDI=?share_link_id=351684285921" target="_blank">Miro</a>
- <a href="https://www.youtube.com/watch?v=0chZFIZLR_0" target="_blank">Git branch, rebase, squesh</a>

_________
### Part I |  GitHub  |  Kamilla
If you want to take your projects home after Piscine:
- Create GitHub account
    - Go to Settings -> SSH and GPG keys
    - Get your SSH key from Shell00 ex03!
    - Go to New SSH key & copy it
    - Go to "Your repositories" -> New (put settings as you want them)
    - After the repo is created, click on green button "Code" on repository page and copy the line under Local -> SSH
    - Clone your repository in terminal
    - Put all folders & files you want into local repo, then git add, commit & push
    - You are done!!

_________
### Part II |  Branches  |  Monika

HEAD -> currently active or checked out branch.

SHA -> Secure Hash Algorithm
- Creating and switching branches:
    - git branch <new_branch_name> -> Creating new branch.
    - git checkout <other_branch> -> checkout is used for many other things, but in this case is used to switch between branches.
    - git switch <other_branch> -> switch has only one purpose, switching between branches.

- Tracking branches:
    - git push -u origin <local_branch> -> publishing existing local branch on a remote repo
    - git checkout --track origin/<existing_branch> -> Creating new local & connecting existing remote branch with each other - remote to local

- Pulling + Pushing Branches (Synchronising your local + remote branches):
    - git pull -> pull commits that you don't have locally (combination of git fetch + git merge)
    - git push -> push commits that you don't have remotely

- Merging branches:
    - git switch main -> change to branch that should receive changes
    - git merge <branch_name> -> name of the branch you want the changes from
      when you merge sometimes you get opened editor and that's because merge sometimes produce new commit and makes standard message "merge branch 'branch_name'"

- Comparing branches:
    - git log main..<branch_name> -> This shows the commits that are in ‘branch_name’
      but not in ‘main’.
    - git log origin/main..main -> This command compares the local ‘main’ with the
      remote-tracking branch ‘origin/main’.

- Deleting branches:
    
    YOU CAN'T DELETE CURRENT HEAD, BRANCH THAT YOU ARE ON!
    - LOCAL:
        - git branch -d <branch_name> -> deleting branches safe.
        - git branch -D <branch_name> -> If you are sure you want to delete it.
    - REMOTE:
        - git push origin --delete <remote_branch_name> -> make sure if you delete
          remote branch to delete also local branch, otherwise it makes no sense.

- Renaming LOCAL branches:
    - git branch -m <new_branch_name> -> rename current, HEAD brunch.
    - git branch -m <old_branch> <new_name> -> non HEAD branch that you want to rename.

- Renaming REMOTE branches:

    DELETING REMOTE BRANCHES -> GIT DON'T ALLOW IT, SO IT'S COMPLICATED

    DELETE FROM REMOTE AND REUPLOAD IT.
    - git push --delete <old_name> -> first delete old remote branch.
    - git push -u origin <new_name> -> then pushing new local branch with new/current name.

_________
### Part III |  Merge conflict  |  Lilie
- Merge conflicts happen when you merge branches that have competing commits, and Git needs your help to decide which changes to incorporate in the final merge.
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/4f53b2ec-6894-4094-83dc-adfc55a517ec" width="600" height="300">

- Live-Demo:
     - create, track & demonstrate side-branch:
        - git branch upgrade
        - git push -u origin upgrade
        - git log & show on network graph
     - change file in main-branch:
        - fix typo in readme
        - git add . + git commit + git push
        - git log & show on network graph
    - change to side-branch & change file:
        - git checkout upgrade
        - upgrade readme file
        - git add . + git commit + git push
        - git log & show on network graph
    - change to main-branch & merge:
        - git checkout main
        - git merge upgrade
        - CONFLICT: manual fix & show auto-resolved position
        - <img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/337650fc-581a-41b2-b086-0d33056a6201" width="600" height="300">
        
        - git add . + git merge --continue + enter commit message + git push
        - git log & show on network graph
- How to avoid conflicts:
    - dont make big changes in main branch
    - if you work with other people:
        - fetch/pull first
        - work on different branches and/or in different files
_________

This is to do list:


- check merge conflict
- && for running 2 commands (first then second)
- how to push to github
- how to branch
- .gitignore file
- git pull = git fetch + git merge:
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/423a6d62-7613-4d21-ba2c-e9d4d87c30b1" heigt="500" width="600">
