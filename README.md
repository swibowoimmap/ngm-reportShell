# [ReportHub](http://reporthub.immap.org)
> 
> Reporting Workflow. Decision Support. Real-Time.
> 
> Developer documentation for local project setup

### Requirements

- Dropbox 33.4.xx
- Vagrant v1.9.xx
- VirtualBox v5.1.xx

# Getting Started

The first steps will be to establish a local development environment on your machine and establish connection with the DEV server.

Steps

1. Install Software Requirements listed above on your local machine
2. Setup Local Project Folders
3. Add to your Dropbox the ``iMMAP AF Team Folder`` [here](https://www.dropbox.com/sh/5eti378yx2qxbxq/AAAFjJkGznjwk8IkZmRkRc7Ma?dl=0)
4. On your local machine, select ``Dropbox 'Settings' > 'Preferences...'``
5. Select ``Account`` tab followed by ```Change Settings...```
6. Navigate to ```iMMAP AF Team Folder/ReportHub/ngm```
5. Unselect the following folders;
	- ``ngm-reportEngine``
	- ``ngm-reportHub``
	- ``ngm-reportPrint``
	- ``ngm-reportShell``
6. Finally select ``Update`` and close
	
	> NOTE: in Dropbox select ```Pause Syncing``` in low bandwidth environments.
	
# Contributing Code

Please review the following links in order to understand how to contribute code to ReportHub repositories

### GitHub Fork & Pull Approach

- [Fork & Pull Approach](https://gist.github.com/Chaser324/ce0505fbed06b947d962)
- [Github Flow](https://guides.github.com/introduction/flow/)


# Vagrant Local Server

With Dropbox folders unselected for sync, run the following commands to setup the local development environment.

Steps
  
1. on the cmd line, navigate to ``ReportHub/ngm`` folder in Dropbox

		$ cd ~/Dropbox/iMMAP\ AF\ Team\ Folder/ReportHub/ngm/ReportHub/ngm
		
2. in ``@ReportHub/ngm`` folder fetch ``ngm-reportShell`` repo 

		$ git clone https://github.com/pfitzpaddy/ngm-reportShell.git
		
3. cd into ``ngm-reportShell``


		$ cd ngm-reportShell
		
4. Update the GitHub repository locations to your forked version of the code

		# UPDATE TO YOUR FORKED REPO!
		sudo git clone https://github.com/<your.fork>/ngm-reportHub.git

5. Run [Vagrant Up](https://www.vagrantup.com/docs/cli/up.html) command

		$ vagrant up
		
	> NOTE: This will take some time to fetch the Ubuntu Lts 14.04 VirtualBox image as well as install server software to establish a replica local server environemnt

5. During install, review VirtualBox configurations in 
	- ``ngm-reportShell/Vagrantfile``
	- ``ngm-reportShell/ngm-reporthub.shell.build.sh``


# Running ReportHub

Once the VirtualBox is completed installation, you can access the configured ReportHub Ubuntu LTS 14.0.4 Virtual Machine via the ``vagrant ssh`` command

Steps

1. Within the ``ngm-reportShell`` folder, ssh into machine

		$ vagrant ssh
		
2. Within the server, navigate to the ``ngm-reportEngine`` repository

		$ cd /home/ubuntu/nginx/www/ngm-reportEngine
		
3. Start the Sails RestAPI application

		$ sudo sails lift

4. Navigate to [http://192.168.33.16](http://192.168.33.16) and ReportHub is running!
