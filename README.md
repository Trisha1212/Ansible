# Ansible


# Install Vagrant
- Vagrant is system controller. Its will download system images so the we can spin our servers quickly.
- Download vagrant - Simple click next next & done(www.vagrantup.com)
- Read more about Vagrant at vagrant website.


# Install VirtualBox
- Virtual Box
- www.virtualbox.org - downloads based on your OS. 

# Check installation done 
- Type `vagrant` to check it installed correctly
- Type `vboxmanage` to check to it installed correctly

# Run vagrant
- https://github.com/Trisha1212/Ansible/blob/vagrant/Vagrantfile
- Copy Vagrantfile in your system and run `vagrant up`
- Check with `vboxmanage list runningvms`

# Install Ansible
## ACS SERVER
- ssh into acs machine `vagrant ssh acs` 
- Install Ansible in debian/ubuntu `sudo apt-get install ansible` 
- Verify ansible is installed correctly`ansible`
- Exit from acs machine `exit`
## WEB SERVER
- ssh into web machine `vagrant ssh web`
- Install ansible in CentOS/Redhat enterprise `sudo yum install epel-release` [Install enterprise linux repo]
- Install Ansible `sudo yum install ansible`
- Verify Ansible is installed correctly `ansible`
- Exit from machine `logout`
## DB SERVER
- SSH into db server/CentOS `vagrant ssh db`
- Can follow above steps for Web server
- Verify Ansible is install correctly `ansible`
- Exit from machine `logout`
## Now you have successfully installed Ansible on all server machine

# TestLab with ansible
- ssh into acs machine `vagrant ssh acs` 
- `vim inventory` 
- Type i 
`
192.168.33.20
192.168.33.30
`
- save the file using wq!
- cat inventory : verify two ipadress

- run ping command using ansible: `ansible 192.168.33.20 -i inventory -u vagrant -m ping -k` <!-- k used to prompt for password --> 
- Type password as `vagrant`
- error for first time as to know fingerprint ! `ssh vagrant@192.168.33.20` click enter
- Type command again `ansible 192.168.33.20 -i inventory -u vagrant -m ping -k`
- Enter password as `vagrant`
- verify the success message with pong returned
