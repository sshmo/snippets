# Remove directory from git but not delete it entirely from the filesystem (local)
    git rm -r --cached myFolder
    echo 'myFolder' >> .gitignore

# Set a new remote and push
    git remote add origin https://github.com/user/repo.git

    # Verify new remote
    git remote -v

    # update local
    git pull origin master

    git push --set-upstream origin master
    git push