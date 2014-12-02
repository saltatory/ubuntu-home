= Ubuntu Post-Install Configuration

Note : this was written for 14.04

= Video drivers

* Download NVIDIA proprietary driver
* At login screen, Ctrl-Alt-F1 to get to a bash prompt
* Shutdown X server
		sudo stop lightdm
* Install driver
		sudo /path/to/driver/NVIDIA-Linux-X86-343.22.run
* Reboot
* Configure displays using Settings -> Displays

= Mandatory packages

* Chrome : http://www.google.com/chrome
** Remove FF from launcher
** Lock Chrome to launcher
** Log into Chrome (optionally remember computer)
** Log into Lastpass (optionally trust computer)

* Install terminator 

		sudo apt-get install terminator

* Install Unity UX tweak tools

		sudo apt-get install unity-tweak-tool gnome-tweak-tool

** Use Unity Tweak Tool -> Launcher to auto-hide the launcher

= Development Tools

* Git
** Install packages
		sudo apt-get install git
** Create and upload new SSH key to GitHub

		mkdir ~/.ssh
		cd ~/.ssh
		ssh-keygen -t rsa -o github-`hostname`

** Modify ssh_config file

		echo "HostName github.com" >> ~/.ssh/config
		echo "IdentityFile github-`hostname`
** Install sexy-bash-prompt 

		(cd sexy-bash-prompt && make install)

* R
** Install programming language

		sudo apt-get install r-base r-recommended

** Install vim

		sudo apt-get install vim

** Install Vundle package manager for vim

		git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim

** Install the vim plugins for R

For more instructions, see : http://www.lepem.ufc.br/jaa/r-plugin.html#r-plugin-installation

** Install RStudio

http://www.rstudio.com/products/rstudio/download/

* Java

		sudo apt-add-repository ppa:webupd8team/java
		sudo apt-get update
		sudo apt-get install oracle-java8-installer

* IntelliJ CE

https://www.jetbrains.com/idea/download/


