# Ansible configuration file
Ansible looks for the global configuration as per the following precedence  

 - $ANSIBLE_CONFIG
 - ./ansible.cfg
 - ~/.ansible.cfg
 - /etc/ansible/ansible.cfg
 
export ANSIBLE_HOST_KEY_CHECKING=True 
That said, we can override settings using <ANSIBLE_HOST_KEY_CHECKING=True>. For example "export ANSIBLE_HOST_KEY_CHECKING=True"  

## Some variables
 - host_key_checking, highly recommended for production i.e. true. For development set false
 - log_path, Default set to null OR set path to log file. Users executing ansible should have write 
 

## Ansible docs
[Here](http://docs.ansible.com/ansible/intro_configuration.html)
