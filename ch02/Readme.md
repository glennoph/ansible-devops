# ch02 first ansible playbook with vagrant
* [ansible 101 episode 1](https://www.youtube.com/watch?v=goclfp6a2IQ&t=2197s)

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
   
```   
PLAY [all] *********************************************************************

TASK [Gathering Facts] *********************************************************
ok: [default]

TASK [ensure chrony is installed] **********************************************
ok: [default]

TASK [ensure chrony is running] ************************************************
ok: [default]

PLAY RECAP *********************************************************************
default                    : ok=3    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```
   
   
## clean

* halt vm
  `vagrant halt`
  
* remove vm
  `vagrant destroy`
  
  
