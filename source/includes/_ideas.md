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
`GET /ideas` or `GET /ideas?tag=foo`

**parameters**

| Name      |     Type |   Description   |
| :-------- | --------:| :------ |
| tag    |   string |  **Optional.**Inquire ideas by tag  |

## Get an idea by id

Get a specific idea, identified by idea ID.

```http
GET /ideas/2 HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
    "id": 2,
    "title": "xx",
    "cover": "http://qiniu.com/test",
    "summary": null,
    "content": "test",
    "content_html": "<p>test</p>\n",
    "stars_count": 0,
    "votes_count": 2
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
  "summary": "test-summary",
  "content": "test-content",
   "cover": "http://qiniu.com/test"
}
```
```http
HTTP/1.1 201 created
Location: http://ideaegg.me/ideas/10

  {
    "id": 2,
    "title": "test-title",
    "cover": "http://qiniu.com/test",
  "summary": "test-summary",
    "content": "test-content",
    "content_html": "<p>test</p>\n",
    "stars_count": 0,
    "votes_count": 2
  }
```

`POST /ideas`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| title    |   string |  **Required.** new idea title  |
| content    |   string |  **Required.** new idea content |
| summary    |   string |  **Required.** new idea summary  |
| cover    |   string |  **Optional.** new idea cover |

## Update idea

Update an idea's title or content owned by the authenticated user.

```http
PUT /ideas/4 HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "title": "test-title2",
  "summary": "test-summary2",
  "content": "test-content2",
   "cover": "http://qiniu.com/test2"
}
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
    "id": 2,
    "title": "test-title2",
    "cover": "http://qiniu.com/test2",
  "summary": "test-summary2",
    "content": "test-content2",
    "content_html": "<p>test-content2</p>\n",
    "stars_count": 0,
    "votes_count": 2
  }
```

`PUT /ideas/:id`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |
| title    |   string |  **Required.** new title  |
| content    |   string |  **Required.** new content |
| summary    |   string |  **Required.** new summary  |
| cover    |   string |  **Optional.** new cover |

## Delete idea

Delete an idea owned by the authenticated user.

```http
DELETE /ideas/4 HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 204 no content
```

`DELETE /ideas/:id`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |

## Like idea

Like an idea by the authenticated user.

```http
PUT /ideas/2/vote HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
    "id": 2,
    "title": "test-title2",
    "cover": "http://qiniu.com/test2",
  "summary": "test-summary2",
    "content": "test-content2",
    "content_html": "<p>test-content2</p>\n",
    "stars_count": 0,
    "votes_count": 3
  }
```

`PUT /ideas/:id/vote`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |

## Unlike idea

Unlike an idea by the authenticated user.

```http
DELETE /ideas/3/vote HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
    "id": 2,
    "title": "test-title2",
    "cover": "http://qiniu.com/test2",
  "summary": "test-summary2",
    "content": "test-content2",
    "content_html": "<p>test-content2</p>\n",
    "stars_count": 0,
    "votes_count": 2
  }
```

`DELETE /ideas/:id/vote`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |

## Star idea

Star an idea by the authenticated user.

```http
POST /ideas/2/star HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
    "id": 2,
    "title": "test-title2",
    "cover": "http://qiniu.com/test2",
  "summary": "test-summary2",
    "content": "test-content2",
    "content_html": "<p>test-content2</p>\n",
    "stars_count": 1,
    "votes_count": 2
  }
```

`PUT /ideas/:id/star`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |

## Unstar idea

Unstar an idea by the authenticated user.

```http
DELETE /ideas/2/star HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
    "id": 2,
    "title": "test-title2",
    "cover": "http://qiniu.com/test2",
  "summary": "test-summary2",
    "content": "test-content2",
    "content_html": "<p>test-content2</p>\n",
    "stars_count": 0,
    "votes_count": 2
  }
```

`DELETE /ideas/:id/star`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |


## Tag idea

Tag an idea by the authenticated user.

```http
PUT /ideas/2/tag HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
```

`PUT /ideas/:id/tag`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |
| tag    |   string |  **Required.** tags, splitted by ',' such as 'software' or 'software, children'  |


## Untag idea

Untag an idea by the authenticated user.

```http
DELETE /ideas/3/tag HTTP/1.1
PRIVATE-TOKEN: your_private_token
```
```http
HTTP/1.1 200 ok
```

`DELETE /ideas/:id/tag`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| id    |   integer |  **Required.** id of the idea  |
| tag    |   string |  **Required.** tags, splitted by ',' such as 'software' or 'software, children'  |