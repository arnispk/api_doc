## Vacancies

### Retrieve all Vacancies

***Request***:
```
GET /v1/vacancies
```
#### Query Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| limit | number | no | Limit the number of results returned by the API. |
| offset | number | no | Sets the record from which results are returned. Usually used with the Limit clause.  |
| output | string | no | The type of output to provide. Available options are 'json' and 'custom'. Defaults to JSON. |
| status | string | no | The vacancy status to return. Available options are 'scheduled', 'open', 'on-hold', 'closed'. If not specified every vacancy is returned. |

### Retrieve one Vacancy by ID

***Request***:
```
GET /v1/vacancies/{id}
```
#### Query Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| id | uuid | yes | The id of the record to return from the API. |

#### Response
