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

*   None

## Update user

Update a user’s avatar, fullname or phone_number by the authenticated user.

```http
PUT /user HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "email": "new_email@qq.com",
  "fullname": "test-fullname",
  "avatar": "http://qiniu.com/test",
  "phone_number": "13800000000"
}

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 15,
  "username": "testtest",
  "email": "new_email@qq.com",
  "fullname": "test-fullname",
  "created_at": "2015-05-23T01:27:56.015Z",
  "phone_number": "13800000000",
  "avatar": "http://qiniu.com/test",
  "private_token": "WwUD85zhd_kMEurVu7SE"
}

```

`PUT /user`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| email | string | **Required.** new email |
| fullname | string | **Required.** new fullname |
| phone_number | string | **Optional.** phone number |
| avatar | string | **Optional.** avatar url |

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

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** The id of a user that will be followed |

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

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** The id of a user that will be unfollowed |

## Get my ideas

Get current user’s ideas.

```http
GET /user/ideas/created HTTP/1.1
PRIVATE-TOken: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json
Link: <http://localhost:3000/api/v2/user/ideas/created?page=1&per_page=24>; rel="first",
      <http://localhost:3000/api/v2/user/ideas/created?page=1&per_page=24>; rel="last"

[
  {
    "id": 8,
    "title": "test-title",
    "cover": null,
    "summary": "test-summary",
    "content": "test-content",
    "stars_count": 0,
    "comments_count": 0,
    "votes_count": 0,
    "author": {
      "id": 11,
      "username": "8ac89167",
      "email": "8ac89167@ideaegg.me",
      "fullname": "8ac89167",
      "created_at": "2015-06-06T02:50:30.447Z",
      "phone_number": null,
      "avatar": null
    },
    "tags": [
      {
        "id": 4,
        "name": "test",
        "taggings_count": 1
      },
      {
        "id": 5,
        "name": "test2",
        "taggings_count": 1
      }
    ]
  }
]

```

`GET /user/ideas/voted`

**Parameters**

*   None

## Get my liked ideas

Get current user’s liked ideas.

```http
GET /user/ideas/voted HTTP/1.1
PROVIATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json
Link: <http://localhost:3000/api/v2/user/ideas/voted?page=1&per_page=24>; rel="first",
      <http://localhost:3000/api/v2/user/ideas/voted?page=1&per_page=24>; rel="last"

[
  {
    "id": 1,
    "title": "Hello",
    "cover": "http://test_image/test.png",
    "summary": "Sirloin leberkas doner pork loin strip steak.",
    "content": "**World**",
    "content_html": "<p><strong>World</strong></p>",
    "stars_count": 11,
    "comments_count": 2,
    "votes_count": 11,
    "author": {
      "id": 1,
      "username": "johndoe1",
      "email": "john1@ideaegg.me",
      "fullname": "John Doe",
      "created_at": "2015-06-06T02:20:40.292Z",
      "phone_number": null,
      "avatar": null
    },
    "tags": [
      {
        "id": 1,
        "name": "test_tag1",
        "taggings_count": 5
      },
      {
        "id": 2,
        "name": "test_tag2",
        "taggings_count": 5
      }
    ]
  }
]

```

`GET /user/ideas/voted`

**Parameters**

*   None

## Get my starred ideas

Get current user’s starred ideas.

```http
GET /user/ideas/starred HTTP/1.1
PROVIATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json
Link: <http://localhost:3000/api/v2/user/ideas/starred?page=1&per_page=24>; rel="first",
      <http://localhost:3000/api/v2/user/ideas/starred?page=1&per_page=24>; rel="last"

[
  {
    "id": 1,
    "title": "Hello",
    "cover": "http://test_image/test.png",
    "summary": "Sirloin leberkas doner pork loin strip steak.",
    "content": "**World**",
    "content_html": "<p><strong>World</strong></p>",
    "stars_count": 11,
    "comments_count": 2,
    "votes_count": 11,
    "author": {
      "id": 1,
      "username": "johndoe1",
      "email": "john1@ideaegg.me",
      "fullname": "John Doe",
      "created_at": "2015-06-06T02:20:40.292Z",
      "phone_number": null,
      "avatar": null
    },
    "tags": [
      {
        "id": 1,
        "name": "test_tag1",
        "taggings_count": 5
      },
      {
        "id": 2,
        "name": "test_tag2",
        "taggings_count": 5
      }
    ]
  }
]

```

`GET /user/ideas/starred`

**Parameters**

*   None

## Modify password

modify password by current password

```http
PUT /user/password HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "current_password": "test_password",
  "password": "new_password",
  "password_confirmation": "new_password"
}

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

`PUT /user/password`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| current_password | string | **Required.** currnet password of the user |
| password | string | **Required.** new password of the user |
| password_confirmation | string | **Required.** new password confirmation |