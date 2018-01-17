# Brainspark API
The *BrainSpark* API is a JSON RPC 2.0 exposed over HTTP.

All operations:
- must use path `/`
- must use http method `POST`
- must include header `Content-Type: application/json`
- must include a valid [JSON RPC 2.0](http://www.jsonrpc.org/specification) payload

###### Example Request
```http
POST / HTTP/1.1
Host: {brainspark_host}
Accept: application/json
Content-Type: application/json

{
    "jsonrpc": "2.0",
    "method": "{service}.{method}",
    "id": "{request_id}",
    "params": {
        "ids": [
            "599a7dba-fb3a-11e7-93d8-a7d489958da0"
        ]
    }
}
```

## Services
See below for a list of API methods grouped by service.

### Account
- [Account.BatchGetAccount](account-batch-get-account.md)
- [Account.BatchGetUser](account-batch-get-user.md)
- [Account.GetAccount](account-get-account.md)
- [Account.GetUser](account-get-user.md)

### Content
- [Content.BatchGetCourse](content-batch-get-course.md)
- [Content.GetCourse](content-get-course.md)

### Participation
- [Participation.BatchGetAttempt](participation-batch-get-attempt.md)
- [Participation.GetAttempt](participation-get-attempt.md)