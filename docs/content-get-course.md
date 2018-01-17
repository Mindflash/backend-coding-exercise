[Back](README.md)

### Get Course

Retrieves a single course by id. A missing course will be designated with a `null` value

###### Method
```
Content.GetCourse
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Content.GetCourse",
	"params": {
		"id": "8d5bee71-9ca4-4cba-90b1-a4345a209b15"
	},
	"id": "21184768-fb41-11e7-a503-0f8d1344d13f"
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
			"id": "8d5bee71-9ca4-4cba-90b1-a4345a209b15",
			"account_id": "b91e575c-8ab0-4114-b11b-d7a06cdbba4f",
			"name": "est"
		}
	},
	"id": "21184768-fb41-11e7-a503-0f8d1344d13f"
}
```

[Back](README.md)