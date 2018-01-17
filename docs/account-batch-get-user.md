[Back](README.md)

### Batch Get Users

Retrieves a set of 1 to 200 users by id. Missing users will be designated with a `null` value

###### Method
```
Account.BatchGetUser
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Account.BatchGetUser",
	"params": {
		"ids": [
			"853629b4-fb40-11e7-a26c-4b5026d382d8",
			"b6feec9c-fb40-11e7-89ce-374290f50084"
		]
	},
	"id": "c73931e4-fb40-11e7-a95f-fb1e838d3f17"
}
```

###### Example Response
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"result": {
		"data": [
			{
				"id": "853629b4-fb40-11e7-a26c-4b5026d382d8",
				"account_id": "21f8c490-2e26-42d0-bbc1-4d4efab6cc4d",
				"email": "Ashley.Gordon@Topicblab.mil",
				"first_name": "Ashley",
				"last_name": "Gordon"
			},
			{
				"id": "b6feec9c-fb40-11e7-89ce-374290f50084",
				"account_id": "b91e575c-8ab0-4114-b11b-d7a06cdbba4f",
				"email": "Frances.Larson@Rhynyx.org",
				"first_name": "Frances",
				"last_name": "Larson"
			}
		]
	},
	"id": "c73931e4-fb40-11e7-a95f-fb1e838d3f17"
}
```

[Back](README.md)