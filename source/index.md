---
title: API Reference

language_tabs:
  - http

toc_footers:
  - <a href='https://github.com/GreenNerd/ideaegg-api/issues'>Raise a question</a>

includes:
  - session
  - ideas
  - users
  - errors

search: true
---

# Introduction

Welcome to the API! If you find someting wrong, you can open a issue on the [github](https://github.com/GreenNerd/ideaegg-api/issues).
<aside class="notice">
  <li>The API uses JSON to serialize data. You <strong>don't need</strong> to specify <strong>.json</strong> at the end of API URL.</li>
  <li>The API in this article is version <strong>2</strong></li>
  <li>API requests <strong>MUST</strong> be prefixed with <strong>api</strong> and the API <strong>version</strong>.</li>
  <li>All exmaples in this article authenticate via header</li>
</aside>

# Explain

## Authentication

Almost all API requests require authentication. You need to pass a `private_token` parameter by URL or header. If passed as header, the header name must be "PRIVATE-TOKEN" (capital and with dash instead of underscore).

If no, or an invalid, `private_token` is provided then an error message will be returned with status code 401:

`{ "message": "401 Unauthorized" }`

Example of a valid API request:

`GET http://ideaegg.me/api/v2/ideas?private_token=QVy1PB7sTxfy4pqfZM1U`

Example for a valid API request using curl and authentication via header:

`curl --header "PRIVATE-TOKEN: QVy1PB7sTxfy4pqfZM1U" "http://ideaegg.me/api/v2/ideas"`


## Pagination

```http
GET /api/v1/ideas?page=2&per_page=10 HTTP/1.1
PRIVATE-TOKEN: your_private_token
```

When listing resources you can pass the following parameters:

- `page` (default: `1`) - page number
- `per_page` (default: `24`, max: `100`) - number of items to list per page

