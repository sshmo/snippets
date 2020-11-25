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
[zsh and Oh My Zsh in Windows 10](https://www.maketecheasier.com/install-zsh-and-oh-my-zsh-windows10/)
[Install Ubuntu on Windows 10](https://ubuntu.com/tutorials/ubuntu-on-windows#1-overview)

**location of zshrc:**
C:\Users\USERNAME\AppData\Local\Packages\{DIST}\LocalState\rootfs\home\{LINUXUSER}\

    {DIST} is equal to CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc
    {LINUXUSER} is the user for which you are looking for the .bashrc
**Install python3**
sudo apt update && sudo apt upgrade
sudo apt upgrade python3
sudo apt install python3-pip


