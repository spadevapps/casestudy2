Software and Components 
-
![Alt image](https://github.com/spadevapps/casestudy2/blob/master/flowchart.png)

- 3 Machines 
	- Metal
	- Master VM
	- Worker VM

- Software 
	- VirtualBox
	- Git
	- Vagrant 
	- Jenkins
	- Ansible
	- Kubernetes (MicroK8s)
	- Grafana 

https://github.com/spadevapps/casestudy2/blob/master
Metal
- 
Install Vagrant

- vagrant init "ubuntu image"
- vagrant up 
- edit vagrant file
	-  make network public to act as bridged adaptor
	-  provision with microk8s and net tools
- vagrant reload

Master VM
-
Software 

- Jenkins 
- Ansible 



Worker VM
- 
- use vagrant to provision with net tools and microk8.
- copy public keys for jenkins user and master user
- configure with ansible playbook, automated by a jenkins pipeline) 




Steps 
- 
- configure vagrant file (metal)
- run vagrant
- add ip for worker to hosts and ansible hosts on master
- add ssh key for jenkins user and sudo user from master to worker
	- ssh keygen
	- ssh-key-copy-id
	- enable sudoless commands for jenkins and vagrant

- ssh into worker to test
- ansible ping worker to test
- make jenkinsfile
- make ansibleplaybook1
	-  starts microk8s
	- copies kubernetes yaml file to microk8s
	- applies yaml file to deploy flaskapp
	![Alt text](https://github.com/spadevapps/casestudy2/blob/master/whatafeeling2.png)

- make jenkins pipeline {master}
	- checkout git
	- run playbook
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/whatagoodfeeling3.png)
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/whatafeeling.png)

- Set Up monitoring  monitoring 
	- port forward Prometheus dashboard and Grafana dashboards

- Add load to Flask app (ctrl+shift+r) and go back to view on monitoring 

![Alt text](https://github.com/spadevapps/casestudy2/blob/master/namespaces1.png)
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/namespaces2.png)
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/top.png)
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/cpuUsage.png)
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/memory.png)
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/network.png)

Before activity 
-
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/beforeactt.png)

After activity
-
![Alt text](https://github.com/spadevapps/casestudy2/blob/master/afteract.png)


Challenges
-
- (RESOLVED) Jenkins user sshing (tried to change name of key and should not have) was still requiring password. 
- (RESOLVED) applying kubernetes on remote server issue "not a path"
	- try copying it to remote server
	- try cloning git on worker then running
	- ansible galaxy?

![Alt image](https://github.com/spadevapps/casestudy2/blob/master/error.png)

- microk8s
	- reset
		- muiltiple nodes running
	- issue with status and start after reset
	- had to manually remove microk8s
		- snap remove microk8s
	- then re provision 
		- vagrant reload --provision







Questions
-
- vagrant default hostname (went from vagrant to localhost)
- configuring vs provisioning 


Cool tricks
-
- pwd in ansible playbook
	- shell out
	-  debug
- copy file to remote





Main Takeaways 
-
- Use the tool for job!
	- i.e. vagrant vs terraform


- DevOps is awesome
	- it was really an incredible experience to the skills acquired over the past 17 weeks pay off.
		-  After all the difficulties encountered with VM's, being able to provision one in seconds with vagrant
		-  After watching countless pipeline builds fail being able to seamlessly automate deployment
		-  And while new bugs were encountered, being able to confidently and efficiently solve them




