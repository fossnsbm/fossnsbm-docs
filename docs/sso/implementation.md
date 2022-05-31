---
id: implementation
title: Implementation
sidebar_label: Implementation
---

# Implementation of sso

below is a example middlwhare for implementation of the Authentication using SSO the type of the OAuth respose is given after the example code


```go
func (h *Handler) OAuthMiddlwhare(next http.Handler) http.Handler {
        return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
                authheader := r.Header["Authorization"]

                if len(authheader) == 0 {
                        // h.sendErrorResponse(w, "Missing Authorization Header", fmt.Errorf("Authorization is required Header"), 401)
                        http.Redirect(w, r, "/api/v1/login", 401)
                        return
                }

                AccessToken := strings.Split(authheader[0], " ")[1]

                resp, err := http.Get(fmt.Sprintf("%s/test?access_token=%s", h.AuthServerURI, AccessToken))

                if err != nil {
                        h.sendErrorResponse(w, "Token Error", err, 401)
                        return
                }

                body, err := ioutil.ReadAll(resp.Body)

                var data types.OAuthRespose
                json.Unmarshal(body, &data)
                defer r.Body.Close()

                // pass the user detailsj
                ctx := context.WithValue(r.Context(), "user", data)
                next.ServeHTTP(w, r.WithContext(ctx))
        })
}
```

type of the OAuth respose

```json
{
    "client_id": "222222",
    "expires_in": 7003,
    "user_email": "john@dasith.works",
    "user_id": "john@dasith.works",
    "user_name": "john",
    "user_roles": [
        {
            "type": "user"
        }
    ]
}

```

This example is taken from 
[https://github.com/fossnsbm/sso/tree/main/example/api](https://github.com/fossnsbm/sso/tree/main/example/api)

if you have any questions about implementation feel free to create a [issue](https://github.com/fossnsbm/sso/issues)

