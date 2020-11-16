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
