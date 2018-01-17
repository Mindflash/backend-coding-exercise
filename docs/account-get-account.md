[Back](README.md)

### Get Account

Retrieves a single account by id. A missing account will be designated with a `null` value

###### Method
```
Account.GetAccount
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Account.GetAccount",
	"params": {
		"id": "21f8c490-2e26-42d0-bbc1-4d4efab6cc4d"
	},
	"id": "00c56456-fb40-11e7-9ffe-4bb811edbd26"
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
			"id": "21f8c490-2e26-42d0-bbc1-4d4efab6cc4d",
			"created_at": "2013-05-29T08:24:48Z",
			"name": "Topicblab"
		}
	},
	"id": "00c56456-fb40-11e7-9ffe-4bb811edbd26"
}
```

[Back](README.md)