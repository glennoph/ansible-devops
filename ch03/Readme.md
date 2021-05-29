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
   ` ansible multi -a "hostname"`
   
   * result:  `192.168.60.4 | UNREACHABLE!` 
   
   
## clean

* halt vm
  `vagrant halt`
  
* remove vm
  `vagrant destroy`
  
  
