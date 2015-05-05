---
title: API Reference

language_tabs:
  - http

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the API! You can use our API to access API endpoints, which can get information in our database.

# Explain

## Authentication

All API requests require authentication. You need to pass a `private_token` parameter by URL or header. If passed as header, the header name must be "PRIVATE-TOKEN" (capital and with dash instead of underscore). You can find or reset your private token in your profile.

If no, or an invalid, `private_token` is provided then an error message will be returned with status code 401:

`{ "message": "401 Unauthorized" }`

Example of a valid API request:

`GET http://ideaegg.me/api/v1/ideas?private_token=QVy1PB7sTxfy4pqfZM1U`

Example for a valid API request using curl and authentication via header:

`curl --header "PRIVATE-TOKEN: QVy1PB7sTxfy4pqfZM1U" "http://ideaegg.me/api/v1/ideas"`

<aside class="notice">
  <li>All exmaples in this article authentication via header</li>
  <li>The API uses JSON to serialize data. You don't need to specify <code>.json</code> at the end of API URL.</li>
  <li>API requests should be prefixed with <code>api</code> and the API version.</li>
</aside>


## Pagination

```http
GET /api/v1/ideas?page=2&per_page=10 HTTP/1.1
PRIVATE-TOKEN: your_private_token
```

When listing resources you can pass the following parameters:

- `page` (default: `1`) - page number
- `per_page` (default: `10`, max: `100`) - number of items to list per page

