# Git&GitHub Workshop

First, that's not really important, but Git doesn't actually record changes, but rather snapshots of our files (at least conceptually; it will use packfiles to store things efficiently and will actually store changes –diffs– in some cases), and will generate diffs on-demand. This sometimes shows in the result of some commands though (like why some commands show one file removed and another added, while other commands show a file being renamed).
- <a href="https://learngitbranching.js.org" target="_blank">Vizualizer</a>
- <a href="https://miro.com/welcomeonboard/ZFdFdXRNNXViZmlYcVpuSUwxbEJlVkhnNlVEa0hZVTY4UlhzelhSQTVqYlYxV1pYbzBna2UySndXMmxFem45NHwzNDU4NzY0NTc1NzUxNTA0Njc5fDI=?share_link_id=351684285921" target="_blank">Miro</a>
- <a href="https://www.youtube.com/watch?v=0chZFIZLR_0" target="_blank">Git branch, rebase, squesh</a>

_________
### Part I |  GitHub
- Bla bla
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/db52c005-1150-4e9e-9797-52f510dfdace" width="600" height="450">

_________
### Part II |  Overview, Branch, marge

General Workflow:
<img src="https://brown-ccv.github.io/honeycomb-docs/assets/images/git_basics-8ba67841533472790a3ef4038aa47323.png" width="600" height="300">
Branching:
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/9996e004-5db5-4f1f-944a-ac431fa4aa16" width="600" height="300">
- git branch -r (-a is all remote and locally)----> to see all remote branches that you don't have locally
- how to pull branches so you have them locally?? (command)
	- create, track and switch at the same time:
		- git checkout -b [local-branch-name] --track origin/[remote-branch-name]
		- git switch -c [local-branch-name] --track origin/[remote-branch-name]
	- create and track but dont't switch to new branch:
		- git branch --track [local-branch-name] origin/[remote-branch-name]


_________
### Part III |  Marge conflict
- Merge conflicts happen when you merge branches that have competing commits, and Git needs your help to decide which changes to incorporate in the final merge.
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/4f53b2ec-6894-4094-83dc-adfc55a517ec" width="600" height="300">
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/337650fc-581a-41b2-b086-0d33056a6201" width="600" height="300">

_________

This is to do list:


- check merge conflict
- && for running 2 commands (first then second)
- how to push to github
- how to branch
- .gitignore file
- git pull = git fetch + git merge:
<img src="https://github.com/LaDeMonika/42_TeamWork/assets/128793184/423a6d62-7613-4d21-ba2c-e9d4d87c30b1" heigt="500" width="600">
