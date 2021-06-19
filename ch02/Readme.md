# ch02 first ansible playbook with vagrant

## prep
0. install Ansible
```
pip3 install ansible

ansible --version 
 ansible [core 2.11.1] 
```

1. install:
   * Vagrant 
https://www.vagrantup.com/downloads

`vagrant --version`
Vagrant 2.2.14

   * update vbguest
`vagrant plugin install vagrant-vbguest`

   * VirtualBox
https://www.virtualbox.org/wiki/Downloads
     - download image & install
	 - start Virtualbox app and check help/about
   
2. Run:
  - cd ch02 ## file:  [Vagrantfile](file:ch02/Vagrantfile)
   `vagrant up`
   
   
3. if there are errors, then run
   `vagrant provision`
   
   ==> default: Running provisioner: ansible...
`playbook` does not exist on the host: /home/glenn/src/github.com/glennoph/ansible-devops/ch02/ansible.playbook
   
   * Messages
```
TASK [ensure chrony is running] ************************************************
fatal: [default]: FAILED! => {"changed": false, "msg": "Could not find the requested service chrony: host"}

PLAY RECAP *********************************************************************
default                    : ok=2    changed=0    unreachable=0    failed=1    skipped=0    rescued=0    ignored=0   

Ansible failed to complete successfully. Any error output should be
visible above. Please fix these errors and try again.

```
   
   
## clean

* halt vm
  `vagrant halt`
  
* remove vm
  `vagrant destroy`
  
  
