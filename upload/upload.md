# Upload small file

- Send small file using form data

### 1. Init form data

Init form data upload

. url: `${imServerUrl}/object/initiate_form_data`
. method: `POST`
. headers:

    - token: im-server token,
    - operationID: unique string

. request body:

json

```
  "name": "file name", // file name must start with userId prefix exp: `3738980700/filename.png`
  "size": 133444 // file size
  "contentType": "file mimetype"
```

. response example

```
{
    "errCode": 0,
    "errMsg": "",
    "errDlt": "",
    "data": {
        "id": "eyJuYW1lIjoiMzczODk4MDcwMC9ZZV9GYW4tODIud2VicCIsInNpemUiOjE1MDMwLCJjb250ZW50VHlwZSI6ImltYWdlL3dlYnAiLCJncm91cCI6IiIsImtleSI6Im9wZW5pbS9kaXJlY3QvMjAyNjAzMjUvMzczODk4MDcwMC8xYzExZDk4MWFkZDI0OThkOGNmMzNhZWVkYzVmMDliNS53ZWJwIn0",
        "url": "http://127.0.0.1:10005/openim",
        "file": "file",
        "header": null,
        "formData": {
            "Content-Type": "image/webp",
            "bucket": "openim",
            "key": "openim/direct/20260325/3738980700/1c11d981add2498d8cf33aeedc5f09b5.webp",
            "policy": "eyJleHBpcmF0aW9uIjoiMjAyNi0wMy0yNVQxMTowNToxMi43MDBaIiwiY29uZGl0aW9ucyI6W1siZXEiLCIka2V5Iiwib3BlbmltL2RpcmVjdC8yMDI2MDMyNS8zNzM4OTgwNzAwLzFjMTFkOTgxYWRkMjQ5OGQ4Y2YzM2FlZWRjNWYwOWI1LndlYnAiXSxbImVxIiwiJHN1Y2Nlc3NfYWN0aW9uX3N0YXR1cyIsIjIwMCJdLFsiZXEiLCIkQ29udGVudC1UeXBlIiwiaW1hZ2Uvd2VicCJdLFsiZXEiLCIkYnVja2V0Iiwib3BlbmltIl0sWyJlcSIsIiR4LWFtei1kYXRlIiwiMjAyNjAzMjVUMDM1NTEyWiJdLFsiZXEiLCIkeC1hbXotYWxnb3JpdGhtIiwiQVdTNC1ITUFDLVNIQTI1NiJdLFsiZXEiLCIkeC1hbXotY3JlZGVudGlhbCIsInJvb3QvMjAyNjAzMjUvdXMtZWFzdC0xL3MzL2F3czRfcmVxdWVzdCJdLFsiY29udGVudC1sZW5ndGgtcmFuZ2UiLCAwLCAxNTAzMF1dfQ==",
            "success_action_status": "200",
            "x-amz-algorithm": "AWS4-HMAC-SHA256",
            "x-amz-credential": "root/20260325/us-east-1/s3/aws4_request",
            "x-amz-date": "20260325T035512Z",
            "x-amz-signature": "dff4d388eec32f88975a432d12898a628c4ba56eb540a3801b405173a7e4eb3b"
        },
        "expires": 1774411512700,
        "successCodes": [
            200
        ]
    }
}
```

### 2. Upload form data to minio

. url: `${minioUrl}` // Get from init form data response, data.url exp: http://127.0.0.1:10005/openim
. request body: all init form data response in formData field

form data

```
  "Content-Type": "image/webp",
  "bucket": "openim",
  "key": "openim/direct/20260325/3738980700/1c11d981add2498d8cf33aeedc5f09b5.webp",
  "policy": "eyJleHBpcmF0aW9uIjoiMjAyNi0wMy....",
  "success_action_status": "200",
  "x-amz-algorithm": "AWS4-HMAC-SHA256",
  "x-amz-credential": "root/20260325/us-east-1/s3/aws4_request",
  "x-amz-date": "20260325T035512Z",
  "x-amz-signature": "dff4d388eec32f88975a432d12898a628c4ba56eb540a3801b405173a7e4eb3b"
  "file": (binary)
```

### 3. Mark upload completed

. url: `${imServerUrl}/object/complete_form_data`
. request body:
json

```
  "name": "file name",
  "id": "eyJuYW1lIjoiMzczODk4MDcwMC9ZZV9GYW4tO...." // Get from init form data response data.id
```

. response example

```
{
    "errCode": 0,
    "errMsg": "",
    "errDlt": "",
    "data": {
        "url": "http://127.0.0.1:10002/object/3738980700/Ye_Fan-82.webp"
    }
}
```
