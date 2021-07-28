---
id: Authentication
title: Authentication 
sidebar_label: Authentication Users
---

## Login API 

The Login API is used authenticate a user in fossnsbm. 

### Authenticate a User 

```
POST /api/login
```
#### Request Headers

#### Request Body

##### Loginid

The login identifier of the user. The identifier can be user email or his username 

#### ipAddress 

The ipAddress of the end user that's login to the fossnsbm. may we be can store the ip address in users login history. 

#### password 

the password of the user 

### Example  


```
{
  "id": "example@fossnsbm.org",
  "password": "password",
  "ipAddress": "192.168.1.42"
}

```

### Example response 

