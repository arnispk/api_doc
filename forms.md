---
layout:default
---

# Forms

## Retrieve all Forms

***Request***:

```
GET /v1/forms
```

### Query Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| type | string | no | The type of form to return. Available options are:<br> * candidate - Returns the candidate apply form definitions. |

## Retrieve one Form by ID

***Request***:

```
GET /v1/forms/{id}
```

### Query Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| id | uuid | yes | The id of the resource to return from the API. |

### Response
