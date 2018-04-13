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
- Run : ```ansible webservers - i inventory_prod -m user -a "name={{username}} password=12345" --sudo ```
