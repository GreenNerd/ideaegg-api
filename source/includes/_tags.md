# Tags

## List tags

Paging list the tags ordered by number of use

```http
GET /tags HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 OK
Link: <http://localhost:3000/api/v2/tags?page=1&per_page=24>; rel="first",
      <http://localhost:3000/api/v2/tags?page=1&per_page=24>; rel="last"
Content-Type: application/json

[
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
```

`GET /tags`

**parameters**

- None

## Query tags

query tags by the name, results will be paging listed

```http
GET /tags/query?name=tag1 HTTP/1.1
PRIVATE-TOKEN: your_private_token

```

```http
HTTP/1.1 200 OK
Link: <http://localhost:3000/api/v2/tags/query?page=1&per_page=24>; rel="first",
      <http://localhost:3000/api/v2/tags/query?page=1&per_page=24>; rel="last"
Content-Type: application/json

[
  {
    "id": 1,
    "name": "test_tag1",
    "taggings_count": 5
  }
]
```

`GET /tags/query`

**parameters**

| Name | Type | Description |
| --- | --- | --- |
| name | string | **Required.** name of the tag |
