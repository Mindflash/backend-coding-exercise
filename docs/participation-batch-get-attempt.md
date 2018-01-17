[Back](README.md)

### Batch Get Attempts

Retrieves a set of 1 to 200 attempts by id. Missing accounts will be designated with a `null` value

###### Method
```
Participation.BatchGetAttempt
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Participation.BatchGetAttempt",
	"params": {
		"ids": [
			"8e73ada3-163c-4bf2-942d-506a9dc007c5",
			"4e2d9e89-d13e-4d8e-8be1-293a9ae69cf4"
		]
	},
	"id": "7550b72e-fb3d-11e7-b300-0361a11d73f7"
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
				"id": "8e73ada3-163c-4bf2-942d-506a9dc007c5",
				"course_id": "09d3984e-2286-4b1b-95bf-271c7ceaaefe",
				"created_at": "2018-01-17T04:16:13.444485198Z",
				"trainee_id": "2405658510"
			},
			{
				"id": "4e2d9e89-d13e-4d8e-8be1-293a9ae69cf4",
				"course_id": "8d5bee71-9ca4-4cba-90b1-a4345a209b15",
				"created_at": "2018-01-17T04:16:13.444869636Z",
				"trainee_id": "0912578565"
			}
		]
	},
	"id": "7550b72e-fb3d-11e7-b300-0361a11d73f7"
}
```



[Back](README.md)