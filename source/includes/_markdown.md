# Markdown

## Convert markdown into html

```http
POST /markdown/preview HTTP/1.1
PRIVATE-TOKEN: your_private_token
Content-Type: application/json

{
  "content": "## title"
}
```
```http
HTTP/1.1 200 ok
Content-Type: application/json

{
  "content": "<h2>title</h2>\n"
}
```

`POST /markdown/preview`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------| :------ |
| content    |   string |  **Required.** the content that is converted into html  |