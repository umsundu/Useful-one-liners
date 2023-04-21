# Useful-one-liners
A collection of useful one liners that I have collected over time to help in extracting data, formatting data etc. 
#Extract usernames or email addresses from any/most files. Mostly used against .txt, html, json files.

## Extract usernames or email addresses from any/most files. Mostly used against .txt, html, json files.

## Syntax: ```grep -E -o "\b[a-zA-Z0-9.-]+@[a-zA-Z0-9.-]+\.[a-zA-Z0-9.-]+\b" filename.json | uniq```

### Example of data within file we want to extract usernames from.
```
cat users.json
{
  "nodes": [
    {
      "id": 400,
      "type": "User",
      "label": "bob-324KL@umsundu.com",
      "props": {
        "highvalue": false,
        "sidhistory": {},
        "passwordnotreqd": false,
        "description": "Service Accounts",
        "sensitive": false,
        "unconstraineddelegation": false,
        "pwdneverexpires": false,
        "enabled": true,
        "hasspn": false,
        "domain": "umsundu.com",
        "pwdlastset": 13607787938,
        "displayname": "bob-324KL",
        "name": "bob-324KL@umsundu.com",
        "lastlogon": -1,
        "distinguishedname": "CN=bob-324KL,OU=*****,DC=umsundu,DC=com",
        "serviceprincipalnames": {},
        "admincount": false,
        "lastlogontimestamp": -1,
        "objectid": "S-1-5-2*********************",
        "dontreqpreauth": false
      },
         {
      "id": 401,
      "type": "User",
      "label": "sue-322JL@umsundu.com",
      "props": {
        "highvalue": false,
        "sidhistory": {},
        "passwordnotreqd": false,
        "description": "Service Accounts",
        "sensitive": false,
        "unconstraineddelegation": false,
        "pwdneverexpires": false,
        "enabled": true,
        "hasspn": false,
        "domain": "umsundu.com",
        "pwdlastset": 13607787938,
        "displayname": "sue-322JL",
        "name": "sue-322JL@umsundu.com",
        "lastlogon": -1,
        "distinguishedname": "CN=sue-322JL,OU=*****,DC=umsundu,DC=com",
        "serviceprincipalnames": {},
        "admincount": false,
        "lastlogontimestamp": -1,
        "objectid": "S-1-5-2*********************",
        "dontreqpreauth": false
      },
```
### Example of running query against the file to extract usernames.  
```
grep -E -o "\b[a-zA-Z0-9.-]+@[a-zA-Z0-9.-]+\.[a-zA-Z0-9.-]+\b" users.json | uniq
bob-324KL@umsundu.com
sue-322JL@umsundu.com
```
