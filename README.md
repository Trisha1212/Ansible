# Ansible
Learning Ansible

# Install Vagrant
-Vagrant is system controller. Its will download system images so the we can spin our servers quickly.
-Download vagrant - Simple click next next & done(www.vagrantup.com)
-Read more about Vagrant at vagrant website.


#Install VirtualBox
-Virtual Box
-www.virtualbox.org - downloads based on your OS. 

#Check installation done 
-Type `vagrant` to check it installed correctly
-Type `vboxmanage` to check to it installed correctly

# Run vagrant
https://github.com/Trisha1212/Ansible
Copy Vagrantfile in your system and run `vagrant up`
Check with `vboxmanage list runningvms`

## Install Ansible
# ACS SERVER
- ssh into acs machine `vagrant ssh acs` 
- Install Ansible in debian/ubuntu `sudo apt-get install ansible` 
- Verify ansible is install `ansible`
- Exit from acs machine `exit`
#WEB SERVER
- ssh into web machine `vagrant ssh web`
- Install ansible in CentOS/Redhat enterprise `sudo yum install epel-release` [Install enterprise linux repo]
- Install Ansible `sudo yum install ansible`
- Verify Ansible is install properly `ansible`
- Exit from machine `logout`
#DB SERVER
- SSH into db server/CentOS `vagrant ssh db`
- Can follow above steps for Web server
- Verify Ansible is install properly `ansible`
- Exit from machine `logout`


### Now you have successfully installed Ansible on all server machine







