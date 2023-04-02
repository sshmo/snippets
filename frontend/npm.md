
# npm

## Using a Node version manager to install Node.js and npm

## Install nvm

```bash
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
    
    export NVM_DIR="$HOME/.nvm"
    
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

## Install node

```bash
    # "node" is an alias for the latest version, this will also update node and npm
    nvm install node
    
    nvm install vx.x.x # install specific version

    nvm use node
    nvm run node --version
    nvm install-latest-npm
    
    # install yarn pkg manager
    npm install -g yarn
```
