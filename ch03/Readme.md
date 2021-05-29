# ch02 ad hoc commands

## prep
1. install:
   * VirtualBox
   * Vagrant 
   * Ansible

   * updates
	 `sudo apt-get install virtualbox-guest-additions-iso`

	 `vagrant plugin install vagrant-vbguest`


2. Run:
   `vagrant up`
   
   
3. if there are errors, then run
   `vagrant provision`
   
   
4. Ad hoc command: 
```
	export ANSIBLE_HOST_KEY_CHECKING=False
	ansible multi -a "hostname"
		
	ansible multi -a "free -h"
	
```

   
   * result:  
```   
   192.168.60.5 | CHANGED | rc=0 >>
orc-app2.test
[DEPRECATION WARNING]: Distribution centos 8.2.2004 on host 192.168.60.4 should use /usr/libexec/platform-python, but is using /usr/bin/python for backward compatibility with 
prior Ansible releases. A future Ansible release will default to using the discovered platform python for this host. See 
https://docs.ansible.com/ansible/2.10/reference_appendices/interpreter_discovery.html for more information. This feature will be removed in version 2.12. Deprecation warnings 
can be disabled by setting deprecation_warnings=False in ansible.cfg.
192.168.60.4 | CHANGED | rc=0 >>
orc-app1.test
[DEPRECATION WARNING]: Distribution centos 8.2.2004 on host 192.168.60.6 should use /usr/libexec/platform-python, but is using /usr/bin/python for backward compatibility with 
prior Ansible releases. A future Ansible release will default to using the discovered platform python for this host. See 
https://docs.ansible.com/ansible/2.10/reference_appendices/interpreter_discovery.html for more information. This feature will be removed in version 2.12. Deprecation warnings 
can be disabled by setting deprecation_warnings=False in ansible.cfg.
192.168.60.6 | CHANGED | rc=0 >>
orc-db.test
```
   
   
## clean

* halt vm
  `vagrant halt`
  
* remove vm
  `vagrant destroy`
  
  
