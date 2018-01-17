[Back](README.md)

### Get Attempt

Retrieves a single attempt by id. A missing attempt will be designated with a `null` value

###### Method
```
Participation.GetAttempt
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Participation.GetAttempt",
	"params": {
		"id": "8e73ada3-163c-4bf2-942d-506a9dc007c5"
	},
	"id": "5f02c94a-fb41-11e7-aee2-b71def56683b"
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
			"id": "8e73ada3-163c-4bf2-942d-506a9dc007c5",
			"course_id": "09d3984e-2286-4b1b-95bf-271c7ceaaefe",
			"created_at": "2018-01-17T04:16:13.444485198Z",
			"trainee_id": "2405658510"
		}
	},
	"id": "5f02c94a-fb41-11e7-aee2-b71def56683b"
}
```

[Back](README.md)