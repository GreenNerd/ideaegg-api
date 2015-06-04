# Users

## Get current user

Get self user

```http
GET /user HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 15,
  "username": "testtest",
  "email": "test@qq.com",
  "fullname": "testtest",
  "created_at": "2015-05-23T01:27:56.015Z",
  "phone_number": null,
  "avatar": null,
  "private_token": "WwUD85zhd_kMEurVu7SE"
}
```

`GET /user`

**Parameters**

- None

## Update user

Update a user's avatar, fullname or phone_number by the authenticated user.

```http
PUT /user HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "fullname": "test-fullname",
  "avatar" : "http://qiniu.com/test",
  "phone_number" : "13800000000"
}
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 15,
  "username": "testtest",
  "email": "test@qq.com",
  "fullname": "test-fullname",
  "created_at": "2015-05-23T01:27:56.015Z",
  "phone_number" : "13800000000"
  "avatar" : "http://qiniu.com/test",
  "private_token": "WwUD85zhd_kMEurVu7SE"
}
```

`PUT /user`

**Parameters**

 Name      |     Type |   Description   |
| :-------- | -------- | :------ |
| fullname    |   string |  **Optional.** new fullname  |
| wechat_openid    |   string |  **Optional.** wechat openid  |
| phone_number    |   string |  **Optional.** phone number  |
| avatar    |   string |  **Optional.** avatar url  |


## Follow user

Follow another user by the authenticated user.

```http
POST /users/2/follow HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
```

`POST /users/:id/follow`

| Name      |     Type |   Description   |
| :-------- | -------- | :------ |
| id    |   integer |  **Required.** The id of a user that will be followed  |

## Unfollow user

Unfollow another user by the authenticated user.

```http
DELETE /users/2/follow HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
```

`DELETE /users/:id/follow`

| Name      |     Type |   Description   |
| :-------- | -------- | :------ |
| id    |   integer |  **Required.** The id of a user that will be unfollowed  |

## Get my ideas

Get current user's ideas.

```http
GET /user/ideas/created HTTP/1.1
PRIVATE-TOken: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

[
  {
    "id": 2,
    "title": "xx",
    "cover": "http://qiniu.com/test",
    "summary": null,
    "content": "test",
    "content_html": "<p>test</p>\n",
    "stars_count": 0,
    "votes_count": 2
  },
  {
    ...
  }
]
```

`GET /user/ideas/voted`

**Parameters**

- None

## Get my liked ideas

Get current user's liked ideas.

```http
GET /user/ideas/voted HTTP/1.1
PROVIATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

[
  {
    "id": 1,
    "title": "xx",
    "cover": "http://qiniu.com/test",
    "summary": null,
    "content": "test",
    "content_html": "<p>test</p>\n",
    "stars_count": 0,
    "votes_count": 2
  },
  {
    ...
  }
]
```

`GET /user/ideas/voted`

**Parameters**

- None

## Get my starred ideas

Get current user's starred ideas.

```http
GET /user/ideas/starred HTTP/1.1
PROVIATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

[
  {
    "id": 1,
    "title": "xx",
    "cover": "http://qiniu.com/test",
    "summary": null,
    "content": "test",
    "content_html": "<p>test</p>\n",
    "stars_count": 0,
    "votes_count": 2
  },
  {
    ...
  }
]
```

`GET /user/ideas/starred`

**Parameters**

- None