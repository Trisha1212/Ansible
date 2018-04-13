# Ansible Module

Run this command : 
- Ansible inbuilt module : `ansible-doc-l` 
- #Comment `ansible-doc ModuleName`
- We need `ansible-doc yum` `ansible-doc service`
```ansible webservers -i inventory -m yum -a "name=httpd state=present" --sudo```
```ansible webservers -i inventory -m service -a "name=httpd enabled=yes state=started" --sudo```
