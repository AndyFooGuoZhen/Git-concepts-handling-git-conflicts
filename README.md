# Fast forward merge 
https://www.youtube.com/watch?v=36ueMx5hro8

Suppose we have a master branch. I branched out master to create a new branch named feature. 
I've made several commits to feature branch and I would like to merge the feature branch to master branch. 
By default, if there are no changes in master branch , and I choose to merge feature branch into it, a fast forward approach will be used. 
It essentially merges all changes from feature to master while making the history of commits linear. 

## Merging without fast forward approach : 
<img width="148" alt="image" src="https://github.com/AndyFooGuoZhen/Git-concepts-handling-git-conflicts/assets/77149531/f67e6feb-9d69-418e-bada-9f9e3c4dcc13">

## Merging with fast forwading:
<img width="147" alt="image" src="https://github.com/AndyFooGuoZhen/Git-concepts-handling-git-conflicts/assets/77149531/831ca58c-3d89-476d-94f5-7bb2f9f713ee">

# git pull vs git fetch
git pull downloads changes from remote repo to local repo and working directory. Changes can be seen immediately. Whereas git fetch only downloads the changes from remote repo to local repo, doesn't show changes in working directory. To get changes reflected at working directory , an additional git merge command is needed.

# git merge master on other branches

## Scenario 1 : Files changed on master is the same set of files changed on branch 
By git pulling origin to main, then checking out to target branch and performing a git merge main, changes from main will be reflected on the new branch. User would have to commit and push the branch to show reflected changes on the new branch on the remote repo.

## Scenario 2 : Files changed on master matches the set of files changed on branch (EX: hello.txt is changed on both branch)
By git pulling origin to main, then checking out to target branch and performing a git merge main, a conflict would occur. Resolve the conflict manually and do a commit and push changes to branch.
