# Ubuntu Post-Install Configuration

Note : this was written for 14.04

# Video drivers

* Download NVIDIA proprietary driver
* At login screen, Ctrl-Alt-F1 to get to a bash prompt
* Shutdown X server
		sudo stop lightdm
* Install driver
		sudo /path/to/driver/NVIDIA-Linux-X86-343.22.run
* Reboot
* Configure displays using Settings -> Displays

# Mandatory packages

* Chrome : http://www.google.com/chrome
	* Remove FF from launcher
	* Lock Chrome to launcher
	* Log into Chrome (optionally remember computer)
	* Log into Lastpass (optionally trust computer)

* Install terminator 

		sudo apt-get install terminator

* Install Unity UX tweak tools

		sudo apt-get install unity-tweak-tool gnome-tweak-tool

* Use Unity Tweak Tool -> Launcher to auto-hide the launcher
* Install and configure network mounts

		sudo mkdir /mnt/vault
	
** Edit /etc/nsswitch.conf. Add "wins" to "hosts:" line
** Add WINS name resolution

		sudo apt-get install winbind

** Edit /etc/fstab as root and add the following

		//TheVault/Public  /media/vault  cifs  guest,uid=1000,iocharset=utf8  0  0

# Development Tools

* Git
	* Install packages

			sudo apt-get install git

	* Create and upload new SSH key to GitHub

			mkdir ~/.ssh
			cd ~/.ssh
			ssh-keygen -t rsa -o github-`hostname`

	* Modify ssh_config file

			echo "HostName github.com" >> ~/.ssh/config
			echo "IdentityFile github-`hostname`
	* Install sexy-bash-prompt 

			(cd sexy-bash-prompt && make install)

* R
	* Install programming language

The extra repository is necessary to get 3.1.x on Ubuntu 14.04. This is a requirement if you want to install packages like "swirl".
		
		sudo apt-get install libcurl4-openssl-dev
		sudo add-apt-repository ppa:marutter/rdev
		sudo apt-get update
		sudo apt-get upgrade
		sudo apt-get install r-base r-recommended

	* Install vim

			sudo apt-get install vim

	* Install Vundle package manager for vim

			git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim

	* Install the vim plugins for R

For more instructions, see : http://www.lepem.ufc.br/jaa/r-plugin.html#r-plugin-installation

	* Install RStudio

http://www.rstudio.com/products/rstudio/download/

* Java

		sudo apt-add-repository ppa:webupd8team/java
		sudo apt-get update
		sudo apt-get install oracle-java8-installer
		sudo apt-get install oracle-java7-installer

* IntelliJ CE

https://www.jetbrains.com/idea/download/

# Safety

* CrashPlan

Download the latest CrashPlan installer from CrashPlan.com

# Aesthetics

* Natural Scrolling

One way to solve this problem is with the following package.

		sudo add-apt-repository ppa:zedtux/naturalscrolling
		sudo apt-get update
		sudo apt-get install naturalscrolling

This reverses scrolling for some programs like web browsers but not for lots of other programs like gnome control panels.

A more thoroughgoing solution can be found here : http://www.maketecheasier.com/reverse-mouse-scrolling-direction-in-ubuntu/

This solution is in the included .Xmodmap file.
