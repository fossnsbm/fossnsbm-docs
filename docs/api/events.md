---
id: events
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
or else we can use the token for authenticate 

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

## check if event exist 

to check if the event exist or not 

```
GET /api/eventexist/{eventid}
```

we can authetnticate user using the token or we can use a api key 

#### Example response 
```
{
   "eventexist": true
}
```
