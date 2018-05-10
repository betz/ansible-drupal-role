# Ansible-Drupal-Role

This is an Ansible role that installs a default Drupal 8 instance and all required configuration and dependancies to support a base Drupal 8 instance. At a high level, this role installs:

- apache2 or nginx
- php
- mariadb
- composer
- drupal 8
- drush
- drupal 8 modules as specified in group_vars/all


### Setup

1. Install ansible:
 
		- sudo apt-get install ansible (Ubuntu) 
		- brew install ansible (macOS)

2. git clone this project

		- git clone https://github.com/johnmcgovern/ansible-drupal-role.git	
	
3. Navigate to project base directory

		- cd ./ansible-drupal-role		

4. Copy hosts.sample to hosts

		- cp hosts.sample hosts

5. Edit hosts file to include desired hosts

		- vi hosts
	
6. Copy group_vars/all.sample to group_vars/all

		- cp group_vars/all.sample group_vars/all

7. Edit group_vars/all variables as appropriate for your enviornment

		- vi group_vars/all


### Usage

1. Ensure that python is installed on the targer server(s)

		- sudo apt-get install python
	
2. Navigate to playbook base directory

		- cd ./ansible-drupal-role
	
3. Run the ansible playbook:

		- ansible-playbook -i hosts site.yml
	
4. Run the ansible playbook limited to certain hosts:

		- ansible-playbook -i hosts --limit=host1 site.yml  #limits to a subset of hosts


### Requirements

1. The Ubuntu target server must already have python installed (Ansible needs it to operate):

		- sudo apt-get install python


### Compatibility

This role is tested on:

- Ubuntu 16.04.4 Server (LTS)
- Ubuntu 17.10 Server
- Ubuntu 18.04 Server (LTS)


### Notes

- The goal of this role is to get to a base Drupal 8 install with no status page errors / issues.


### ToDo

- Enable php.ini best-practices and tunning for group_vars/all
- Fix hash salt randomness generation (currently static)
- Fix the ability to seperate Web and DB server (broken now)


### Contact

- john@johnmcgovern.com
- https://www.johnmcgovern.com

