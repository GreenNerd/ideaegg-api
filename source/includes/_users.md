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

## Get single user

Get a specific user, identified by idea ID.

```http
GET /users/1 HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 1,
  "username": "john_smith",
  "fullname": "john_smith",
  "avatar" : "http://qiniu.com/xxx",
  "level" : 0,
  "money" : 0,
  "ideas_count" : 0,
  "comments_count" : 0,
  "followees_count" : 0,
  "followers_count" : 0,
  "liked_ideas_count" : 0,
  "email": "john@example.com",
  "phone_number" : "13800000000",
  "sign_up_type" : "wechat", // wechat or web
  "created_at": "2013-09-30T13: 46: 02Z",
  "updated_at": "2013-09-30T13: 46: 02Z"
}
```

`GET /users/:id`

| Name      |     Type |   Description   |
| :-------- | -------- | :------ |
| id    |   integer |  **Required.**The id of a user  |

## Update user

Update a user's username, fullname or email by the authenticated user.

```http
PUT /users/1 HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "username": "test-username",
  "fullname": "test-fullname",
  "wechat_openid": "1234asdadfafadsf",
  "avatar" : "http://qiniu.com/test",
  "level" : 0,
  "money" : 0,
  "ideas_count" : 0,
  "email": "john@example.com",
  "phone_number" : "13800000000"
}
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 1,
  "username": "test-username",
  "fullname": "test-fullname",
  "avatar" : "http://qiniu.com/test",
  "level" : 0,
  "money" : 0,
  "ideas_count" : 0,
  "comments_count" : 0,
  "followees_count" : 0,
  "followers_count" : 0,
  "liked_ideas_count" : 0,
  "email": "john@example.com",
  "phone_number" : "13800000000",
  "sign_up_type" : "wechat", // wechat or web
  "created_at": "2013-09-30T13: 46: 02Z",
  "updated_at": "2013-09-30T13: 46: 02Z"
}
```

`PUT /users/:id`

**Parameters**

 Name      |     Type |   Description   |
| :-------- | -------- | :------ |
| id    |   integer |  **Required.**The id of a user  |
| username    |   string |  **Optional.** new username  |
| fullname    |   string |  **Optional.** new fullname  |
| email    |   string |  **Optional.** new email  |
| wechat_openid    |   string |  **Optional.** wechat openid  |
| level    |   string |  **Optional.** user level, default is 0  |
| money    |   string |  **Optional.** user money, default is 0  |
| phone_number    |   string |  **Optional.** phone number  |
| avatar    |   string |  **Optional.** avatar url  |


