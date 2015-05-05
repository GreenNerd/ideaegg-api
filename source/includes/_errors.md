# Errors

The API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your private token is wrong
403 | Forbidden -- The request is without permission
404 | Not Found -- The requested resource does not exist
422 | Unprocessable -- Fail to validate
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
