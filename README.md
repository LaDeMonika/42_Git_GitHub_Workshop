# Git&GitHub Workshop

#### Kamila: GitHub

#### Monika: Branches

#### Lilie: Conflicts

_________

Useful links: 
- <a href="https://learngitbranching.js.org" target="_blank">Vizualizer</a>
- <a href="https://www.youtube.com/watch?v=2qwx59b25V4" target="_blank">Use git on your personal device [.gitconfig]</a>
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
      <br>
        <img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/337650fc-581a-41b2-b086-0d33056a6201" width="600" height="300">
      <br>
      <br>
      
        - git add . + git merge --continue + enter commit message + git push
        - git log & show on network graph
- How to avoid conflicts:
    - dont make big changes in main branch
    - if you work with other people:
        - fetch/pull first
        - work on different branches and/or in different files

<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/423a6d62-7613-4d21-ba2c-e9d4d87c30b1" heigt="500" width="600">
