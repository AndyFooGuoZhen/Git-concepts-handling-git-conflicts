# Fast forward merge 
https://www.youtube.com/watch?v=36ueMx5hro8

Suppose we have a main branch. I branched out main to create a new branch named feature. 
I've made several commits to feature branch and I would like to merge the feature branch to main branch. 
By default, if there are no changes in main branch , and I choose to merge feature branch into it, a fast forward approach will be used. 
It essentially merges all changes from feature to main while making the history of commits linear. 

## Merging without fast forward approach : 
<img width="148" alt="image" src="https://github.com/AndyFooGuoZhen/Git-concepts-handling-git-conflicts/assets/77149531/f67e6feb-9d69-418e-bada-9f9e3c4dcc13">

## Merging with fast forwading:
<img width="147" alt="image" src="https://github.com/AndyFooGuoZhen/Git-concepts-handling-git-conflicts/assets/77149531/831ca58c-3d89-476d-94f5-7bb2f9f713ee">

# git pull vs git fetch
git pull downloads changes from remote repo to local repo and working directory. Changes can be seen immediately. Whereas git fetch only downloads the changes from remote repo to local repo, doesn't show changes in working directory. To get changes reflected at working directory , an additional git merge command is needed.

# git merge main on other branches

## Scenario 1 : Files changed on main is the same set of files changed on branch 
By git pulling origin to main, then checking out to target branch and performing a git merge main, changes from main will be reflected on the new branch. User would have to commit and push the branch to show reflected changes on the new branch on the remote repo.

## Scenario 2 : Files changed on main matches the set of files changed on branch, merge main into branch first (EX: hello.txt is changed on both branch)
By git pulling origin to main, then checking out to target branch and performing a git merge main, a conflict would occur. Resolve the conflict manually and do a commit and push changes to branch. Then we can merge the branch to main via a pull request, no conflicts should be present here since we resolved it when merging main to our branch.

## Scenario 3 : Files changed on main matches the set of files changed on branch, merge branch into main
Directly making a pull request to merge firstBranch into main will cause a git conflict. After resolving the conflict and merging the firstBranch to main, the contents for main and firstBranch will be changed as well.
