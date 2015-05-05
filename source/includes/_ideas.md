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
| :-------- | --------:| :------ |
| tag    |   string |  **Optional.**Inquire ideas by tag  |

## Get an idea by id

Get a specific idea, identified by idea ID.

```http
GET /ideas/4 HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

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
  }
}
```

`GET /ideas/:id`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------:| :------ |
| id    |   integer |  **Required.**The id of an idea  |

## Create idea

Creates a new idea owned by the authenticated user.

```http
POST /ideas HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "title": "test-title",
  "content": "test-content"
}
```
```http
HTTP/1.1 201 created
Location: http://ideaegg.me/ideas/10

{
  "id": 10,
  "title": "test-title",
  "content": "test-content",
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
  }
}
```

`POST /ideas`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| title    |   string |  **Required.** new idea title  |
| content    |   string |  **Required.** new idea content |
| public    |   boolean |  **Optional.** true or false  |
| level    |   integer |  **Optional.** idea's level, default is 0  |

## Update idea

Update an idea's title or content owned by the authenticated user.

```http
PUT /ideas/4 HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "title": "test-title",
  "content": "test-content"
}
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 4,
  "title": "test-title",
  "content": "test-content",
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
  }
}
```

`PUT /ideas/:id`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |
| title    |   string |  **Required.** new title  |
| content    |   string |  **Required.** new content |
| public    |   boolean |  **Optional.** true or false  |
| level    |   integer |  **Optional.** idea's level, default is 0  |
