# Scaling out with Multiple inventory files

- vagrant ssh acs : Installation of Tree : `sudo apt-get install tree` && `apt-get update`
- Run : tree

```
.
|-- production
|   |-- group_vars
|   |   |-- all
|   |   |-- db
|   |   `-- webservers
|   |-- host_vars
|   |   `-- web1
|   `-- inventory_prod
`-- test
    |-- group_vars
    |   |-- all
    |   `-- db
    |-- host_vars
    |   `-- web1
    `-- inventory_test

6 directories, 9 files
````
- `cd production` `cat inventory_prod` and its a same inventory file which we used in our last excersice
- ``` cd group_vars``` 
- ``` vim all```
```
---
#This is our user
username : all_username
```
- Comment : when we run this file under host_vars : web1 should not be present 
- Run : ```ansible webservers -i inventory_prod -m user -a "name={{username}} password=12345" --sudo ```
- output :
```
web1 | success >> {
    "append": false, 
    "changed": false, 
    "comment": "", 
    "group": 504, 
    "home": "/home/web1_user", 
    "move_home": false, 
    "name": "web1_user", 
    "password": "NOT_LOGGING_PASSWORD", 
    "shell": "/bin/bash", 
    "state": "present", 
    "uid": 503
}
````
### Order of precendence :
- When inside group_vars all [only]  is present the output will be ``` "home": "/home/all_username",```
- When inside group_vars groups & all is present the output will be ``` "home": "/home/group_user" ```
- When inside host_vars web1 is present the output will be ``` "home": "/home/web1_user" ```
