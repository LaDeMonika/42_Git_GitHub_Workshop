# Git workflow
### Part II |  Branches


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

-----------------------------------------------------------
- Deleting branches:
    
    YOU CAN'T DELETE CURRENT HEAD, BRANCH THAT YOU ARE ON!
    - LOCAL:
        - git branch -d <branch_name> -> deleting branches safe.
        - git branch -D <branch_name> -> If you are sure you want to delete it.
    - REMOTE:
        - git push origin --delete <remote_branch_name> -> make sure if you delete
          remote branch to delete also local branch.

-----------------------------------------------------------

- Renaming LOCAL branches:
    - git branch -m <new_branch_name> -> rename current, HEAD brunch.
    - git branch -m <old_branch> <new_name> -> non HEAD branch that you want to rename.

- Renaming REMOTE branches:
    - git push --delete <old_name> -> first delete old remote branch.
    - git push -u origin <new_name> -> then pushing new local branch with new/current name.

- Comparing branches:
    - git log main..<branch_name> -> This shows the commits that are in ‘branch_name’
      but not in ‘main’.
    - git log origin/main..main -> This command compares the local ‘main’ with the
      remote-tracking branch ‘origin/main’.
