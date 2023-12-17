---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
[https://www.nobledesktop.com/learn/git/git-branches](https://www.nobledesktop.com/learn/git/git-branches)  
[https://docs.gitlab.com/ee/user/project/merge_requests/squash_and_merge.html](https://docs.gitlab.com/ee/user/project/merge_requests/squash_and_merge.html)  
  
[https://stackoverflow.com/questions/2765421/how-do-i-push-a-new-local-branch-to-a-remote-git-repository-and-track-it-too](https://stackoverflow.com/questions/2765421/how-do-i-push-a-new-local-branch-to-a-remote-git-repository-and-track-it-too)  
  
[https://www.makeuseof.com/git-reset-single-file/](https://www.makeuseof.com/git-reset-single-file/)  
  
[https://javascript.plainenglish.io/the-quickest-way-to-become-a-better-developer-715c338a1cee](https://javascript.plainenglish.io/the-quickest-way-to-become-a-better-developer-715c338a1cee)  
  
[https://github.com/github/gitignore](https://github.com/github/gitignore)  
  
[https://github.com/codecrafters-io/build-your-own-x](https://github.com/codecrafters-io/build-your-own-x)  
  
git pull origin develop  
  
cp [source] [destination]  
mv [options] [current file name] [new file name]  
mv is for move but can rename with just to params  
mv example1.txt example2.txt  
rm  
  
  
git status // see changes  
git branch -a //list branch  
  
  
git checkout develop  
git branch newBranch basedOnCurrentBranch  
git branch -d localBranchName  
git checkout newBranch  
git push --set-upstream origin branchNAME  
  
revert commit  
git log list commit  
git revert commitID  
  
  
when merging to develop branch after code review do git squash on github site in merge pull down  
  
  
when you merge develop -> your working branch, this is to keep your branch up-to-date. Because you need a shared commit history, merging develop -> your branch MUST be done with a normal commit merge.  
  
when you merge your branch -> develop, this is to add your work to the code base. this must be done with a squash merge in order to keep a clean commit history  
  
squash can be used with out merge  
  
update branch to latest  
git checkout develop  
git pull  
git checkout previousBranch  
git stash if uncommitted changes or staged changes ????  
git merge develop  
  
git stash # To add changes to stash stack  
git stash list # Shows list of stashed changes  
git stash apply stash@{0} # Retrieve stash  
git stash clear # Clear stash list  
  
git add –A  
git commit -m "changed thing"  
git push