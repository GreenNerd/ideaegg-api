# Feedback

## create a feedback

```http
POST /products/1/feedbacks HTTP/1.1
PRIVATE-TOKEN: your_private_token

{
  "body": "this is a body",
  "stars": 5,
  "images": [
    "www.baidu.com/picture.png",
    " www.test.com/image.png"
  ],
  "contact": "xx@qq.com",
  "anonymous": false
}

```

```http
HTTP/1.1 201 OK
Content-Type: application/json

{
  "id": 4,
  "body": "this is a body",
  "stars": 5,
  "images": [
    "www.baidu.com/picture.png",
    " www.test.com/image.png"
  ],
  "contact": "xx@qq.com",
  "anonymous": false,
  "product": {
    "id": 1,
    "name": "test_name"
  }
}
```

`POST /products/:id/feedbacks`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| body | string | **Required.** body of feedback |
| stars | integer | **Required.** stars of feedback(value in 0-5) |
| images | array | **Optional.** images of feedback |
| contact | string | **Optional.** user contact |
| anonymous | boolean | **Optional.** if anonymous |