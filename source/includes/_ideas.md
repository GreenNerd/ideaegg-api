# Ideas

## List ideas

Get a list of ideas by the authenticated user.

```http
GET /ideas HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 OK
Link: <http://localhost:3000/api/v2/ideas?page=1&per_page=24>;rel="first",
      <http://localhost:3000/api/v2/ideas?page=1&per_page=24>; rel="last"
Content-Type: application/json

[
  {
    "id": 6,
    "title": "test-title",
    "cover": null,
    "summary": "test-summary",
    "content": "test-content",
    "content_html": "<p>test-content</p>\ ",
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
    "tags": []
  },
  {
    "id": 5,
    "title": "Hello",
    "cover": "http://test_image/test.png",
    "summary": "Sirloin leberkas doner pork loin strip steak.",
    "content": "**World**",
    "content_html": "<p><strong>World</strong></p>\ ",
    "stars_count": 10,
    "comments_count": 1,
    "votes_count": 10,
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

`GET /ideas` or `GET /ideas?tag=foo`

**parameters**

| Name | Type | Description |
| --- | --- | --- |
| tag | string | **Optional.**Inquire ideas by tag |

## Get an idea by id

Get a specific idea, identified by idea ID.

```http
GET /ideas/1 HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 1,
  "title": "Hello",
  "cover": "http://test_image/test.png",
  "summary": "Turkey doner bacon capicola salami strip steak.",
  "content": "**World**",
  "content_html": "<p><strong>World</strong></p>\\\n",
  "comments_count": 1,
  "stars_count": 10,
  "votes_count": 10,
  "starred": false,
  "voted": false,
  "author": {
    "id": 1,
    "username": "johndoe1",
    "email": "john1@ideaegg.me",
    "fullname": "John Doe",
    "created_at": "2015-08-09T01:20:55.119Z",
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

```

`GET /ideas/:id`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.**The id of an idea |

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
Content-Type: application/json

{
  "id": 6,
  "title": "test-title",
  "cover": "http://qiniu.com/test",
  "summary": "test-summary",
  "content": "test-content",
  "content_html": "<p>test-content</p>\ ",
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
  "tags": [ ]
}

```

`POST /ideas`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| title | string | **Required.** new idea title |
| content | string | **Required.** new idea content |
| summary | string | **Required.** new idea summary |
| cover | string | **Optional.** new idea cover |
| tag | string | **Optional.** add tags for the idea. eg. “tag1,tag2” |

## Update idea

Update an idea’s title or content owned by the authenticated user.

```http
PUT /ideas/1 HTTP/1.1
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
  "id": 1,
  "title": "test-title2",
  "cover": "http://qiniu.com/test2",
  "summary": "test-summary2",
  "content": "test-content2",
  "content_html": "<p>test-content2</p>\n ",
  "stars_count": 10,
  "comments_count": 1,
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

```

`PUT /ideas/:id`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |
| title | string | **Required.** new title |
| content | string | **Required.** new content |
| summary | string | **Required.** new summary |
| cover | string | **Optional.** new cover |

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

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |

## Like idea

Like an idea by the authenticated user.

```http
PUT /ideas/1/vote HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 1,
  "title": "Hello",
  "cover": "http://test_image/test.png",
  "summary": "Sirloin leberkas doner pork loin strip steak.",
  "content": "**World**",
  "content_html": "<p><strong>World</strong></p>\ ",
  "stars_count": 10,
  "comments_count": 1,
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

```

`PUT /ideas/:id/vote`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |

## Unlike idea

Unlike an idea by the authenticated user.

```http
DELETE /ideas/1/vote HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 1,
  "title": "Hello",
  "cover": "http://test_image/test.png",
  "summary": "Sirloin leberkas doner pork loin strip steak.",
  "content": "**World**",
  "content_html": "<p><strong>World</strong></p>\ ",
  "stars_count": 10,
  "comments_count": 1,
  "votes_count": 10,
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

```

`DELETE /ideas/:id/vote`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |

## Star idea

Star an idea by the authenticated user.

```http
PUT /ideas/1/star HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

  {
  "id": 1,
  "title": "Hello",
  "cover": "http://test_image/test.png",
  "summary": "Sirloin leberkas doner pork loin strip steak.",
  "content": "**World**",
  "content_html": "<p><strong>World</strong></p>\ ",
  "stars_count": 11,
  "comments_count": 1,
  "votes_count": 10,
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

```

`PUT /ideas/:id/star`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |

## Unstar idea

Unstar an idea by the authenticated user.

```http
DELETE /ideas/1/star HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 1,
  "title": "Hello",
  "cover": "http://test_image/test.png",
  "summary": "Sirloin leberkas doner pork loin strip steak.",
  "content": "**World**",
  "content_html": "<p><strong>World</strong></p>\ ",
  "stars_count": 10,
  "comments_count": 1,
  "votes_count": 10,
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

```

`DELETE /ideas/:id/star`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |

## Tag idea

Tag an idea by the authenticated user.

```http
POST /ideas/8/tags HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "tag": "tag1, tag2"
}

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

[
  {
    "id": 4,
    "name": "test",
    "taggings_count": 1
  },
  {
    "id": 5,
    "name": "test2",
    "taggings_count": 1
  },
  {
    "id": 6,
    "name": "tag1",
    "taggings_count": 1
  },
  {
    "id": 7,
    "name": "tag2",
    "taggings_count": 1
  }
]

```

`POST /ideas/:id/tags`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |
| tag | string | **Required.** tags, splitted by ’,’ such as ‘software’ or 'software, children’ |

## Untag idea

Untag an idea by the authenticated user.

```http
POST /ideas/8/untags HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "tag": "tag1, tag2"
}

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

[
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

```

`POST /ideas/:id/untags`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |
| tag | string | **Required.** tags, splitted by ’,’ such as 'software’ or 'software, children’ |

## Get a idea’s comments

Return the comments ordered by created time

```http
GET /ideas/1/comments HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 ok
Content-Type: application/json
Link: <http://localhost:3000/api/v2/ideas/1/comments?page=1&per_page=24>; rel="first",
    <http://localhost:3000/api/v2/ideas/1/comments?page=1&per_page=24>; rel="last"

[
  {
    "id": 1,
    "body": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit.",
    "body_html": "<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>\ ",
    "created_at": "2015-06-06T02:20:54.174Z",
    "idea_id": 1,
    "user": {
      "id": 1,
      "username": "johndoe1",
      "email": "john1@ideaegg.me",
      "fullname": "John Doe",
      "created_at": "2015-06-06T02:20:40.292Z",
      "phone_number": null,
      "avatar": null
    }
  }
]

```

`GET /ideas/:id/comments`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |

## Make a comment on the idea

```http
POST /ideas/1/comments HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "body": "this is a body"
}

```

```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "id": 7,
  "body": "test",
  "body_html": "<p>test</p>\ ",
  "created_at": "2015-06-08T01:15:58.530Z",
  "idea_id": 1,
  "user": {
    "id": 11,
    "username": "8ac89167",
    "email": "8ac89167@ideaegg.me",
    "fullname": "8ac89167",
    "created_at": "2015-06-06T02:50:30.447Z",
    "phone_number": null,
    "avatar": null
  }
}

```

`POST /ideas/:id/comments`

**Parameters**

| Name | Type | Description |
| --- | --- | --- |
| id | integer | **Required.** id of the idea |
| body | string | **Required.** content of the comment |