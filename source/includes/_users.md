# Users

## List users

Get a list of users by the authenticated user.

```http
GET /users HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

[
  {
    "id": 1,
    "username": "john_smith",
    "email": "john@example.com",
    "fullname": "john_smith",
    "avatar" : "http://qiniu.com/xxx",
    "level" : 0,
    "money" : 0,
    "ideas_count" : 0,
    "comments_count" : 0,
    "followees_count" : 0,
    "followers_count" : 0,
    "liked_ideas_count" : 0
  },
  {
    ...
  }
]
```

`GET /users`

**Parameters**

- None