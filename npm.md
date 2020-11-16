# Using a Node version manager to install Node.js and npm

# Install nvm

    export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Install node
    nvm install node # "node" is an alias for the latest version
    nvm use node
    nvm run node --version
    nvm install-latest-npm