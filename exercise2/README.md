#Inventory File 
- Can be located any where file system and as long as path is located

# Inventory features
- Behavioural parameter : Config , ssh user, ssh pass, private key files.
- Groups : Test db server / production server
- Groups of groups : Test server / production server/ location based : east server/ west server
- Assign Variables: Syslog should not sent to across multiple server and it should be local to server
- Scaling out using multiple files:
- Static /Dynamic :





# Step 1 : Copy this file in your local 
- Running only webservers : `ansible webservers -i inventory -m ping`
- Running database servers : `ansible dbservers -i inventory -m ping`
- Running group of groups : `ansible datacenter -i inventory -m ping`

# output :
```web1 | success >> {
    "changed": false, 
    "ping": "pong"
}

db1 | success >> {
    "changed": false, 
    "ping": "pong"
}
```

[comment]: 
- If we dont assign [datacenter:children] it will consider webservers & dbservers as system
- [datacenter:vars] vars is used for assigning variable.

