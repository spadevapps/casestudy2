Metal
- 
Install Vagrant file

- vagrant init "ubuntu image"
- vagrant up 
- edit vagrant file
	-  make network public to act as bridged adaptor
	-  provision with microk8s and net tools

Master VM
-
Software 
-
- Jenkins
- Ansible 
- elk stack 


worker vm
-
- set up with net tools and microk8.
- has public keys for jenkins user and master user
- ...




steps 
- 
- configure vagrant file (metal)
- run vagrant
- add ip for worker to hosts and ansible hosts on master
- add ssh key for jenkins user and sudo user from master to worker
	- ssh keygen
	- ssh-key-copy-id

- ssh into worker to test
- ansible ping worker to test








Challenges
-
- Jenkins user sshing (tried to change name of key and should not have) was still requiring password. 
- ...







question
-
- vagrant default hostname (went from vagrant to localhost)
- ...

