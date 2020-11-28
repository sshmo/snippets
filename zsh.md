# Install zsh

	sudo apt update
	sudo apt install zsh
	zsh --version
	sudo apt install git-core curl fonts-powerline 

# Install oh-my-zsh
	sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh"
	default? no

# Themes
	https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
	ZSH_THEME="eastwood"
	#robbyrussell
	#gnzh
	#af-magic
	
# Add the bin folder to $PATH before the plugins load

[zsh-virtualenv-setup.md](https://gist.github.com/dixneuf19/a398c08f00aac24609c3cc44c29af1f0#file-zsh-virtualenv-setup-md)
	PATH=$HOME/.local/bin:$PATH

# plugins
	https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/
	plugins=(
		git
		z
		virtualenvwrapper
		virtualenv
		)
		#cp
		#colored-man-pages 
		#colorize

# Python Environment Handling

	export WORKON_HOME=$HOME/.venvs
	export PROJECT_HOME=$HOME/Devel
	export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
	export VIRTUALENVWRAPPER_VIRTUALENV_ARGS=' -p /usr/bin/python3 '
	source /home/shab/.local/bin/virtualenvwrapper.sh
	export VIRTUAL_ENV_DISABLE_PROMPT=
	
# Zsh for win 10

[WSL2 consumes massive amounts of RAM and power!!](https://github.com/microsoft/WSL/issues/4166)

**To turn off wsl(Vmmem) > Powershell>

	wsl --shutdown

Configure memory usage with .wslconfig:

	C:\Users\<yourUserName>\.wslconfig
	
	# write in .wslconfig:
	[wsl2]
	memory=2GB # Limits VM memory in WSL to 2 GB
	processors=2 # Makes the WSL 2 VM use two virtual processors


[zsh and Oh My Zsh in Windows 10](https://www.maketecheasier.com/install-zsh-and-oh-my-zsh-windows10/)

[Install Ubuntu on Windows 10](https://ubuntu.com/tutorials/ubuntu-on-windows#1-overview)

[Python for web development on Windows](https://docs.microsoft.com/en-us/windows/python/web-frameworks)

**location of zshrc:**
C:\Users\USERNAME\AppData\Local\Packages\{DIST}\LocalState\rootfs\home\{LINUXUSER}\

    {DIST} is equal to CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc
    {LINUXUSER} is the user for which you are looking for the .bashrc
    
**Install python3**

	sudo apt update && sudo apt upgrade
	sudo apt upgrade python3 python3-pip
	pip3 install --user virtualenv virtualenvwrappe


