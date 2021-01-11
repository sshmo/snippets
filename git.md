# Show git configs
    cat .git/config

# Pull new remote branch:
    git checkout -b other-branch
    git fetch origin other-branch
    git merge origin other-branch

# 5 Steps for Code Changes Only on Git Branch and Merge to Master Once Done
    ['5 Steps for Code Changes Only on Git Branch and Merge to Master Once Done'](https://www.thegeekstuff.com/2019/03/git-create-dev-branch-and-merge/)

# Remove directory/file from git but not delete it from the filesystem (local)
    git rm --cached filename
    git rm -r --cached myFolder
    echo 'myFolder' >> .gitignore

# Set a new remote and push

    # if the folder is empty:
    git clone https://github.com/user/repo.git
    git config user.name user_name
    git config user.email user_email


    # if git init or folder is already a git repo
    git remote add origin https://github.com/user/repo.git

    # Verify new remote
    git remote -v

    # update local
    git pull origin master

    git push --set-upstream origin master
    git push


# Delete a local repository
    
    Delete the .git directory in the root-directory of your repository to delete the git-related information (branches, versions).

# Git refusing to merge unrelated histories
    --allow-unrelated-histories
    

# When working with others, 
    #stash local changes before pulling in order to avoid conflict commits.
    git stash
    git pull 
    git stash pop #Reapply my local changes, eventually merge confl

# Fatal: failed to read object XXX : Permission denied fatal: the remote end hung up unexpectedly (WSL)
    sudo chown -R <user>: .git
    chmod -R u+rwX .git

# Missing or invalid credentials. Error: connect ECONNREFUSED
    on linux, just add sudo before the command

# error: Your local changes to the following files would be overwritten by merge:
        README.md
        Please commit your changes or stash them before you merge.
        Aborting
    git checkout HEAD README.md
    git push
