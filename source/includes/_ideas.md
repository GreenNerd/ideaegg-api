# Ideas

## List ideas

Get a list of ideas by the authenticated user.

```http
GET /ideas HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "id": 4,
    "title": "hello",
    "content": "world",
    "public" : true,
    "created_at": "2013-09-30T13: 46: 02Z",
    "updated_at": "2013-09-30T13: 46: 02Z",
    "comments_count": 0,
    "cached_votes_up": 0,
    "stars_count": 0,
    "author": {
      "id": 1,
      "username": "john_smith",
      "fullname": "john_smith",
      "avatar": "http://qiniu.com/xxx"
    },
    "tags" : {
      "foo"
    }
  },
  {
    ...
  }
]
```
`GET /ideas` or `GET /ideas?tag=foo`

**parameters**

| Name      |     Type |   Description   |
| :-------- | --------:| :------: |
| tag    |   string |  **Optional.**Inquire ideas by tag  |


