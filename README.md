# Using Git

### Basic commands
    git init
    git clone <url>
    git log
    git log -n 1                 -> shows only last commit
    git log --oneline            -> compact version, each commit in one line
    git log --graph --oneline
    git diff <id1> <id2>
    git diff --stat <id1> <id2>  -> shows diff statistics
    git diiff                    -> shows diff between working area and staging area	
    git diff --staged            -> shows diff between repop and staging
    git status
    git commit -m "message"
    git add <file>
    git add                      -> adds all changes
    git checkout <branch>
    git branch
    git merge <branch>           -> merges <branch> into current
    git merge <branch_source> <branch_dest>
    git merge --abort
    git push


    git remote -> shows the remotes
    git remote -v -> shows also urls
    git remote add <remote_name> <url>     -> adds a remote, use "origin" as remote_name if main 
    git push <remote> <branch>             -> sync current repo to remote (svn commit)
    git pull <remote> <branch>             -> sync remote to current repo (svn update)
    git fetch <remote>                     -> syncs remote to the local "<remote>/master" branch
    eg.:
      git pull origin master               -> equivalent witthe fetch+merge (can be used when there
                                              are no vonflicts)
      ---> if there are conflicts do this:
      git fetch origin
      git merge master origin/master	-> resolve conflicts hereBAsi

### Sync github fork
    
    git clone git@github.com:vargaandrea/FORKED_REPO.git
    cd into/cloned/fork-repo
    git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git
    git fetch upstream
    git pull upstream master

    Sync from browser:
    https://github.com/KirstieJane/STEMMRoleModels/wiki/Syncing-your-fork-to-the-original-repository-via-the-browser
