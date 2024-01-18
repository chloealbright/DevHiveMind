---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
when forking avoid adding collaborators to keep pull request permissions otherwise any collaborator on the project can make a request and merge without master repo approval

pull request is for code review & is not exclusively a git feature it is a github feature

you should always be downstream 

squash merge squash all your commits to one in git history of main branch 

commit frequently be with intent and test frequently 

 ```bash
git checkout feature/dev-78_post_letter  

git checkout feature/dev-80_get_by_id_letter_endpoint  

git merge --squash feature/dev-78_post_letter  
```

do small changes in branches because of dependencies

draft pr instead of pr 
Note that draft PRs are not available in all types of GitHub repository. For details, see the GitHub documentation on draft PRs.

dealt with merge conflict


