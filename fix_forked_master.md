### Initial problem
Forked a gitgub repo.
I made the change that I did not create a branch for my personal commits, but I committed them directly into my master. 
Since pull requests include all changes between the my fork and the upstram repo, I cannot really do a pull request without also including my personal commits (and that is not what I want). 

### Question 
How do I bring my master to be fully in sync with upstream? Note: if I sync with upstram, the changed in upstream will be pulled/merged into my master, but my changes will still be there, preventing me to do a pull request.  

### Solution
1. Create a branch of your master from the point where still everything was okay (before my first commit). 
See: https://stackoverflow.com/questions/2816715/branch-from-a-previous-commit-using-git.
I have used the second option, on the github.com interface. Named it new_master.
1. Make new_master the default branch (github.com: Settings -> Branches)
See: https://help.github.com/articles/setting-the-default-branch/ 
1. Make:
    * master to old_master
    * new_master to master

    Command line solution:
    ```
    git branch -m master old_master
    git branch -m new_master master

    git push origin :master old_master
    git push origin :new_master master
    ```
1. Delete new_master local and remote:
    ```
    git branch -d new_master
    git push --delete origin new_master
    
    ```
1. Now sync the master (which is now way behind the upstream repo), 
   via github.com: https://github.com/KirstieJane/STEMMRoleModels/wiki/Syncing-your-fork-to-the-original-repository-via-the-browser, 
   or command line (check if the remotes are okay and then pull):
    ```
    git remote -v
    git pull upstram master
    ```
    Now you have a master again fully in sync with the upstream master.
    You can create a branch from it, do your changes and make a PR.
    
### Moral of the story
Always make a branch for your changes :D.
