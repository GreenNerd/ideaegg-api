# Sessions

## Sign up

Sign up to register new user

```http
POST /sign_up HTTP/1.1
Content-Type: application/json

{
  "username": "john_smith",
  "email": "john@example.com",
  "password": "test1234",
  "apassword_confirmation": "test1234"
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "username": "john_smith",
  "email": "john@example.com",
  "fullname": "john_smith",
  "private_token": "dd34asd13as",
  "created_at": "2012-05-23T08:00:58Z"
}
```

`POST /sign_up`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------:| :------ |
| username    |   string |  **Required**.The username of user  |
| email   |   string |  **Required**.The email of user |
| password    |   string |  **Required**.User password  |
| password_confirmation    |   string |  **Required**. User password confirmation  |

## Sign in

Sign in to get private token

```http
POST /sign_in HTTP/1.1
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "test1234"
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "username": "john_smith",
  "email": "john@example.com",
  "fullname": "john_smith",
  "private_token": "dd34asd13as",
  "created_at": "2012-05-23T08:00:58Z"
}
```

`POST /sign_in`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------:| :------ |
| login    |   string |  **Required**.The login of user: username or email  |
| password   |   string |  **Required**.Valid password |

## Sign in with wechat

```http
POST /sign_in_with/wechat HTTP/1.1
Content-Type: application/json

{
  "uid": "test_uid"
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 1,
  "username": "john_smith",
  "email": "john@example.com",
  "fullname": "john_smith",
  "private_token": "dd34asd13as",
  "created_at": "2012-05-23T08:00:58Z"
}
```

`POST /sign_in_with/wechat`

**Parameters**

| Name      |     Type |   Description   |
| :-------- | --------:| :------ |
| uid    |   string |  **Required**.The openid of wechat  |
| username   |   string |  **Optional**. The username of user.if no, the endpoint will generates one |
| email   |   string |  **Optional**. The email of user.if no, the endpoint will generates one |