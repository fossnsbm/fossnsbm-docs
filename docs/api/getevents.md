---
id: get events
title: get events
sidebar_label: get events
---

This endpoint is used to retrieve details of the public or priavte events of the user 

```
GET /api/events
```

we can maybe provice the api key inside the headers o

```
apikey: {API-KEY}
```
or else we can use the token to authenticate 

### response 

```
[
   {
      "id": "e-1",
      "title": "example event",
      "description": "Something",
      "public": "yes",
      "members": [String]
   }
]

```
