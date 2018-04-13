# Step 1 : Copy this file in your local 
- Running only webservers : `ansible webservers -i inventory -m ping`
- Running database servers : `ansible dbservers -i inventory -m ping`
- Running group of groups : `ansible datacenter -i inventory -m ping`

## If we dont assign [datacenter:children] it will consider webservers & dbservers as system
## [datacenter:vars] vars is used for assigning variable.
