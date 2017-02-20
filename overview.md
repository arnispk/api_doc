---
layout: default
---

[Home](index)

# Overview

## API Endpoints

```
https://ats-central.endouble.net/v1
```
## API Conventions

* API versioning is handled using a major version number in the URL, e.g. /api/v1/endpoint.
* /something is equivalent to /something/.
* URL paths, URL query parameter names, and JSON field names are case sensitive.
* Query parameters and JSON fields use underscore.
* The HTTP status indicates whether an operation failed or succeeded, with extra information included in the HTTP response body.
* All APIs return standard error code formats.
* Unexpected query parameters are ignored.
* Unexpected JSON fields in the request body are ignored.

## Authentication

* To authenticate with the APIs you need to specify the “Authorization” header with each request. The value of the "Authorization" header must be a valid API key. You can also perform basic auth with the API key as username and an empty password. 
* Administrators can create a new account and provide you an API Key. You cannot recover an API key after it has been created.
* Every request to the API server is done through HTTPS, your credentials are as secure as the encrypted connection.

## Errors

When you make an API call you may receive an error message in response. Either there is something wrong with your request or something went wrong on our end.

```
422 Unprocessable Entity
```
```json
{
    "errors": [
        {
            "code": "422",
            "message": "required field is missing",
            "description": "firstName is required"
        }
    ]
}
```

## Error Table

| Code | Status Name | Description |
|---|---|---|
| 200 | OK | Successful HTTP request. |
| 201 | CREATED | The request has been fulfilled, resulting in the creation of a new resource. |
| 202 | ACCEPTED | The request has been accepted for precessing, but the processing has not been completed. |
| 204 | NO_CONTENT | The server successfully processed the request and is not returning any content. |
| 400 | BAD_REQUEST | The server cannot or will not process the request due to an apparent client error. |
| 401 | UNAUTHORIZED | User is not authorized. |
| 403 | FORBIDDEN | The request was a valid request, but the server is refusing to respond to it. |
| 404 | NOT_FOUND | The requested resource could not be found but may be available in the future. |
| 405 | NOT_ALLOWED | The method specified is not allowed for the resource identified. |
| 422 | UNPROCESSABLE | Content type is understood but unable to process contained instructions. |
| 500 | INTERNAL_SERVER_ERROR | Generic error message, given when an unexpected condition was encountered. |
| 501 | NOT_IMPLEMENTED | The server either does not recognise the request method, or it lacks the ability to fulfil the request. |
| 503 | SERVICE_UNAVAILABLE | The server is currently unavailable (because it is overloaded or down for maintenance). |
