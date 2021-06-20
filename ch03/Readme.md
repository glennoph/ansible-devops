# ch03 ad hoc commands

1. Setup:
   * Vagrantfile 
   * Ansible

   * updates
	 `sudo apt-get install virtualbox-guest-additions-iso`

	 `vagrant plugin install vagrant-vbguest`
	 `vagrant plugin install vagrant-cachier` ## to speed up vagrant

2. Run:

```
vagrant up
vagrant status
```   
   
4. Ad hoc command: 

```
ansible multi -i inventory -a "hostname" ## do ont use inventory file

#	export ANSIBLE_HOST_KEY_CHECKING=False

ansible multi -a "hostname"
		
ansible multi -a "free -h"
	
```

   
   * result:  
```
[DEPRECATION WARNING]: Distribution centos 8.4.2105 on host 192.168.60.4 should use /usr/libexec/platform-python, but is using 
/usr/bin/python for backward compatibility with prior Ansible releases. A future Ansible release will default to using the discovered 
platform python for this host. See https://docs.ansible.com/ansible/2.11/reference_appendices/interpreter_discovery.html for more 
information. This feature will be removed in version 2.12. Deprecation warnings can be disabled by setting deprecation_warnings=False in 
ansible.cfg.
192.168.60.4 | CHANGED | rc=0 >>
orc-app1.test
[DEPRECATION WARNING]: Distribution centos 8.4.2105 on host 192.168.60.6 should use /usr/libexec/platform-python, but is using 
/usr/bin/python for backward compatibility with prior Ansible releases. A future Ansible release will default to using the discovered 
platform python for this host. See https://docs.ansible.com/ansible/2.11/reference_appendices/interpreter_discovery.html for more 
information. This feature will be removed in version 2.12. Deprecation warnings can be disabled by setting deprecation_warnings=False in 
ansible.cfg.
192.168.60.6 | CHANGED | rc=0 >>
orc-db.test
[DEPRECATION WARNING]: Distribution centos 8.4.2105 on host 192.168.60.5 should use /usr/libexec/platform-python, but is using 
/usr/bin/python for backward compatibility with prior Ansible releases. A future Ansible release will default to using the discovered 
platform python for this host. See https://docs.ansible.com/ansible/2.11/reference_appendices/interpreter_discovery.html for more 
information. This feature will be removed in version 2.12. Deprecation warnings can be disabled by setting deprecation_warnings=False in 
ansible.cfg.
192.168.60.5 | CHANGED | rc=0 >>
orc-app2.test

```
   * Ad Hoc command table 
 
 `ansible multi -a 'hostname'`
   
   
| Command  | Use                     |
|----------|-------------------------|
| hostname | display hostname        |
| date     | check time and timezone |
| free -h  | available memory in vm  |
|          |                         |

   * Module setup to gather vm info
     `ansible db -m setup | less` ## get setup info for db server 
   * Module yum to install package on servers
     `ansible multi -b -m yum -a 'name=ntp state=present' `
   
5. Ansible fork

   * NB add deprecation_warnings=False to ansible.cfg file to avoid DEPRECATION WARNING 

   * Default fork is 5
   * Set fork to 1 - so the commands are not run in parallel
   `ansible multi  -a 'hostname' -f 1`

```
192.168.60.4 | CHANGED | rc=0 >>
orc-app1.test
192.168.60.5 | CHANGED | rc=0 >>
orc-app2.test
192.168.60.6 | CHANGED | rc=0 >>
orc-db.test
```
   
## clean

* halt vm

`vagrant halt`
  
* remove vm - force

`vagrant destroy -f`
  
  
