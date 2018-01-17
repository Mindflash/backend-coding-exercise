[Back](README.md)

### Batch Get Accounts

Retrieves a set of 1 to 200 accounts by id. Missing accounts will be designated with a `null` value

###### Method
```
Account.BatchGetAccount
```

###### Example Request
```http
POST / HTTP/1.1
Host: {brainsparkHost}
Content-Type: application/json

{
    "jsonrpc": "2.0",
    "method": "Account.BatchGetAccount",
    "params": {
        "ids": [
            "599a7dba-fb3a-11e7-93d8-a7d489958da0",
            "bec784b6-fb3b-11e7-9b5b-0bc91e981e31"
        ]
    },
    "id": "c4e0bf8a-fb3f-11e7-8241-0faf4421c718",
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
                "id": "599a7dba-fb3a-11e7-93d8-a7d489958da0",
                "name": "foo",
                "domain": "foo.mindflash.com"
            },
            {
                "id": "bec784b6-fb3b-11e7-9b5b-0bc91e981e31",
                "name": "bar",
                "domain": "bar.mindflash.com"
            }
        ]
    },
    "id": "c4e0bf8a-fb3f-11e7-8241-0faf4421c718"
}
```

[Back](README.md)