---
id: introduction
title: Introduction
sidebar_label: Introduction
---

# OAuth 2.0 Server

## Protocol Flow

```
     +--------+                               +---------------+
     |        |--(A)- Authorization Request ->|   Resource    |
     |        |                               |     Owner     |
     |        |<-(B)-- Authorization Grant ---|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(C)-- Authorization Grant -->| Authorization |
     | Client |                               |     Server    |
     |        |<-(D)----- Access Token -------|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(E)----- Access Token ------>|    Resource   |
     |        |                               |     Server    |
     |        |<-(F)--- Protected Resource ---|               |
     +--------+                               +---------------+
```

Based on [RFC 6749](https://tools.ietf.org/html/rfc6749) implementation


**Authorization Request**:
[http://localhost:9096/authorize?client_id=000000&response_type=code](http://localhost:9096/authorize?client_id=000000&response_type=code)

**Grant Token Request**:
[http://localhost:9096/token?grant_type=client_credentials&client_id=000000&client_secret=999999&scope=read](http://localhost:9096/token?grant_type=client_credentials&client_id=000000&client_secret=999999&scope=read)

```json
{
  "access_token": "J86XVRYSNFCFI233KXDL0Q",
  "expires_in": 7200,
  "scope": "read",
  "token_type": "Bearer"
}
```
