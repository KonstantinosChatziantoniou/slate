---
title: Embneusys

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This is the Embneusys Rest API for the clients' website. 

# Authentication


Users are authenticated using the Firebase API. Each request to the API must be accompanied with the User ID and the authentication Token provided by the Firebase.


<aside class="notice">
Firebase API may be replaced with custom authentication in the future.
</aside>

# Devices

## Get All Devices


> The above command returns JSON structured like this:

```json
[
  {
    "total_devices": 3,
    "device_uid": [127128, 812712, 1829912],
    "tool_name": ["jackhammer", "motor 1", "motor 2"] }
]

OR 
[
  {
    "total_devices": 3,
    "device_uid": 127128,
    "tool_name": "jackhammer" 
  },
  {
    "total_devices": 3,
    "device_uid":  812712, 
    "tool_name": "motor 1"
  },
  {
    "total_devices": 3,
    "device_uid": 1829912,
    "tool_name":  "motor 2"
  }
]


```

This endpoint retrieves all devices owned by a specific user.

### HTTP Request

`GET http://example.com/api/devices`

### Query Parameters

Parameter |  Description
--------- |  -----------
uid | User id  .
token | Authentication Token.


## Get History of a Specific Device



> The above command returns JSON structured like this:

```json
{
  "value": 12,
  "dateID" : 14
}
```

This endpoint retrieves the measurements of a specific device.


### HTTP Request

`GET http://example.com/devices/<ID>`

### URL Parameters

Parameter | Default |  Description
--------- | ------- |  -----------
ID | | The ID of the device to retrieve
history | 0 | Returns the nth oldest measurement. Zero for the most recent.

# Account Management

 
##  Login

This endpoint validates the user and returns an authentication token for this session
### HTTP Request

> The above command returns JSON structured like this:

```json
{ 
    "jwt": "ahsIdsasadHBY8SAasHhjjas",
    "expires": 120
}
```

`POST http://example.com/login/`

### Body Parameters

Parameter |   Description
--------- |   -----------
usernsame |  The username or email of the user
password  |  The password encrypted


<aside class="warning"> This endpoint is not currently in use. This is for future reference.</aside>

## Logout


This endpoint terminates the session for the user (deletes the auth token from the server)

> The above command returns JSON structured like this:

```json
{ 
    "logedOut": true
}
```

### HTTP Request 
`POST http://example.com/login/`

### Body Parameters

Parameter |   Description
--------- |   -----------
userId |  The user's ID
token  |  The authentication token


<aside class="warning"> This endpoint is not currently in use. This is for future reference.</aside>


## Create Account


This endpoint terminates the session for the user (deletes the auth token from the server)

> The above command returns JSON structured like this:

```json
{ 
    "logedOut": true
}
```

### HTTP Request 
`POST http://example.com/login/`

### Body Parameters

Parameter |   Description
--------- |   -----------
username |  User's name
password  |  The password
email | 
companyName |
phone1 | 
phone2 |
address |



<aside class="warning"> This endpoint is not currently in use. This is for future reference.</aside>

