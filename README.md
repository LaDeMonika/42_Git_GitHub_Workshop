# Git&GitHub Workshop

#### Kamila: GitHub

#### Monika: Branches

#### Lilie: Conflicts

_________

Useful links:
- <a href="https://learngitbranching.js.org" target="_blank">Vizualizer</a>
- <a href="https://www.youtube.com/watch?v=2qwx59b25V4" target="_blank">Use Git&GitHub on your personal device [gitconfig]</a>
- <a href="https://www.youtube.com/watch?v=l2yrJtwoC_E&t=1373s">Learn Git and GitHub Tutorial For Beginners | Full Course [2024]</a>
- <a href="https://www.youtube.com/watch?v=0chZFIZLR_0" target="_blank">Git branch, rebase, squesh</a>
_________
### Part I |  GitHub  |  Kamilla
If you want to take your projects home after Piscine:
- Create GitHub account
    - Go to Settings -> SSH and GPG keys
    - Get your SSH key from Shell00 ex03!
        - Even if the project is finished, you can still clone your repository from project page
        - IF that doesn't work for some reason: you can find your SSH key on computer.
            - Go to Home directory, in settings select: Show hidden files
            - Look for the folder: .ssh
            - Open id_rsa.pub (your PUBLIC key) and it is inside
    - Go back to GitHub, select New SSH key & copy it
    - Now go to "Your repositories" & select New (put settings as you want them)
    - After the repo is created, click on green button "Code" on repository page and copy the line under Local -> SSH
    - Clone your repository in terminal
    - Put all folders & files you want into local repo, then git add, commit & push
        - If you are copying from another local repository, be careful not to copy the .git folder
    - You are done!!

There is also a way to link the remote repository you created now with your local repos that are already linked to your 42 remote repos.
Like this you can select where to push. This process is a little bit more complicated but you can follow this guide by one of the 42 students:
https://github.com/francisrafal/42-connect-multiple-remotes-tutorial

(I never did this though but I'm also still not using VSCode change is scary)

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
    - git merge <branch_name> -> name of the branch you want the changes from.

      when you merge sometimes you get opened editor and that's because merge sometimes produce new commit and makes standard message "merge branch 'branch_name'"

_________
### Part III |  Merge conflict  |  Lilie
- Merge conflicts happen when you merge branches that have competing commits, and Git needs your help to decide which changes to incorporate in the final merge.
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/4f53b2ec-6894-4094-83dc-adfc55a517ec" width="600" height="300">

- Live-Demo of resolving local merge conflict between main-branch and side-branch:
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

- Instead of merging you can also rebase. What is the difference?
    - merge: combines two commit histories and creates a new commit "merge"
        - syntax: when you're in the main-branch type "git merge <side_branch>" -> this means: "merge side-branch into the main-branch"
    - rebase: changes the commit history of one branch, so that it looks like there were never diverging commits. instead if will "put on commit on top of the other". 
        - syntax: when you're in the side-branch type "git rebase <main_branch>" -> this means: "rebase the side-branch onto the main-branch"
        - this command will move the base of the side-branch to the tip of the main-branch and rewrite the commit history of the side-branch.
        - with rebase you usually have to use "git push --force" afterwards to push it to your remote repository. so be very careful with this command, because it will also overwrite the remote commit history!

- How to avoid conflicts, especially if you work in a team:
    - work on different branches and/or in different files
    - avoid working directly on main branch, and if you do, only implement small changes. 
    - always fetch/pull first before you push your changes

### Part IV |  Other useful commands  |  Lilie
- going back to an older version:
    - git reset --hard origin/<branch_name> -> resets everything to the version of the remote repo of current branch
    - git reset --hard <commit_ID> -> resets everything to the commit that you specify with <commit_ID>
    - git reset --soft <commit_ID> -> resets your commit history to the commit you specify, but keeps the changes you made afterwards. so it's like uncommiting everything after <commit_ID>
    - git restore --staged <file> -> unstages <file>, so it's like un-doing "add <file>"

