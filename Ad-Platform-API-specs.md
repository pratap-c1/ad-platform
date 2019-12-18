[<< Back to HOME](README.md)

1. [Login](#login)

## Login

#### To call server APIs a token is required. To get this token using the below mentioned login API

We will share the `email` and `password` with you.

Login API retruns a `token` which you can use in rest of the APIs 

    /login [POST]
    
HEADER

    Content-Type:application/json
    
BODY
```javascript
{
  "email": "string",  // required
  "password": "string" // required
}
```

RESPONSE - code - 200
```javascript
{
  "result": {
    "token": <authToken>,
    "user": {UserModel}
  },
  "name": null,
  "code": null,
  "message": null  
}
```
