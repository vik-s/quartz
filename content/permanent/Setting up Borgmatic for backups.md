---
title: "Setting up Borgmatic for backups"
created: 2022-10-15 14:31
status: #permanent
tags: #homelab
---

[[Borgmatic]] is a wrapper for 
Install borg

Create a virtual environment for borg
			`virtualenv --python=python3 borg-env`
			
Activate the borg env
		`source borg-env/bin/activate`
		
Install the dependancies for debian/ubuntu
		`sudo apt-get install python3 python3-dev python3-pip python-virtualenv libssl-dev openssl libacl1-dev libacl1 build-essential`
		 `sudo apt-get install libfuse-dev fuse pkg-config`    # optional, for FUSE support
	
Install borg with pip
			`pip install borgbackup[fuse]` # with fuse support
			`pip install borgbackup`# without fuse support
			
Add path to `borg` in the PATH variable for root user (borg will run as root because we want to back up system directories too)
		`export PATH=/home/vik/borg-env/bin:$PATH`
		
Install borgmatic
	`sudo pip3 install --upgrade borgmatic` -- this is a global install which results in a less cleanly separated python environment, but that is ok for now.

Generate borgmatic config
	`sudo generate-borgmatic-config`

Edit the config file at `/etc/borgmatic/config.yaml` to suit your needs

Validate borgmatic config
	`sudo validate-borgmatic-config`
	
Initialize borg repo if one does not already exist.
	`sudo borgmatic init --encryption repokey`
	
Run a backup
	`sudo borgmatic --verbosity 1 --files`
	
Schedule backup job
- Create a file called `borgmatic` in `/etc/cron.d`
- Add the following line in it and save
	`0 3 * * * root PATH=$PATH:/usr/bin:/usr/local/bin /root/.local/bin/borgmatic --verbosity -1 --syslog-verbosity 1`
- Set the file to be executable
	`sudo chmod +x /etc/cron.d/borgmatic`

---
# References

https://torsion.org/borgmatic/