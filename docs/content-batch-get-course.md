[Back](README.md)

### Batch Get Courses

Retrieves a set of 1 to 200 courses by id. Missing courses will be designated with a `null` value

###### Method
```
Content.BatchGetCourse
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
	"jsonrpc": "2.0",
	"method": "Content.BatchGetCourse",
	"params": {
		"ids": [
			"09d3984e-2286-4b1b-95bf-271c7ceaaefe",
			"8d5bee71-9ca4-4cba-90b1-a4345a209b15"
		]
	},
	"id": "a68b90c0-fb3d-11e7-8f96-c3e7a9bbe7cf"
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
				"id": "09d3984e-2286-4b1b-95bf-271c7ceaaefe",
				"account_id": "21f8c490-2e26-42d0-bbc1-4d4efab6cc4d",
				"name": "odit"
			},
			{
				"id": "8d5bee71-9ca4-4cba-90b1-a4345a209b15",
				"account_id": "b91e575c-8ab0-4114-b11b-d7a06cdbba4f",
				"name": "est"
			}
		]
	},
	"id": "a68b90c0-fb3d-11e7-8f96-c3e7a9bbe7cf"
}
```


[Back](README.md)