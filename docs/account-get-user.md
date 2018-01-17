[Back](README.md)

### Get User

Retrieves a single user by id. A missing user will be designated with a `null` value

###### Method
```
Account.GetUser
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Account.GetUser",
	"params": {
		"id": "b6feec9c-fb40-11e7-89ce-374290f50084"
	},
	"id": "ce4f68f4-fb40-11e7-91da-83ae2b86bcab"
}
```

###### Example Response
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"result": {
		"data": {
            "id": "b6feec9c-fb40-11e7-89ce-374290f50084",
            "account_id": "b91e575c-8ab0-4114-b11b-d7a06cdbba4f",
            "email": "Frances.Larson@Rhynyx.org",
            "first_name": "Frances",
            "last_name": "Larson"
        }
	},
	"id": "ce4f68f4-fb40-11e7-91da-83ae2b86bcab"
}
```

[Back](README.md)