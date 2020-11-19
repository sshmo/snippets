# Using a Node version manager to install Node.js and npm

# Install nvm

    export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Install node
    # "node" is an alias for the latest version
    # this will also update node and npm
    nvm install node 

    nvm use node
    nvm run node --version
    nvm install-latest-npm