## what is this
You can start api sever immediately

## reference
https://www.pluralsight.com/guides/token-based-authentication-with-ruby-on-rails-5-api

# useage

```
make up
```

# try

```
$ curl -H "Content-Type: application/json" -X POST -d '{"email":"example@mail.com","password":"123123123"}' http://localhost:3000/authenticate
```
Your token will now be returned.
```
{"auth_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJleHAiOjE0NjA2NTgxODZ9.xsSwcPC22IR71OBv6bU_OGCSyfE89DvEzWfDU0iybMA"}
```
You can NOT reachable "resource" without token

```
$ curl http://localhost:3000/items
{"error":"Not Authorized"}
```

You can only reachable "resource" with token all the time

```
$ curl -H "Authorization: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJleHAiOjE0NjA2NTgxODZ9.xsSwcPC22IR71OBv6bU_OGCSyfE89DvEzWfDU0iybMA" http://localhost:3000/items
[]
```