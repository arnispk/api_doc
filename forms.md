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

```json
{
    "nextUpdate": "0000-00-00 00:00:00",
    "data": [
        {
            "id": "b72262d6-26e8-4130-b25c-11e46effa269",
            "type": "candidate",
            "fields": [
            {
                "element": "input",
                "attributes": {
                    "name": "first_name",
                    "required": "required",
                    "type": "text"
                }
            },
            {
                "element": "input",
                "attributes": {
                    "name": "last_name",
                    "required": "required",
                    "type": "text",
                    "maxlength": "255"
                }
            },
            {
                "element": "input",
                "attributes": {
                    "name": "email",
                    "required": "required",
                    "type": "email"
                }
            },
            {
                "element": "input",
                "attributes": {
                    "name": "phone",
                    "type": "tel"
                }
            },
            {
                "element": "select",
                "attributes": {
                    "name": "sample_choice",
                    "multiple": "multiple"
                },
                "children": [
                    {
                        "element": "optgroup",
                        "attributes": {
                            "label": "Group A"
                        },
                        "children": [
                            {
                                "element": "option",
                                "attributes": {
                                    "value": "A1",
                                    "label": "Choice A1"
                                }
                            },
                            {
                                "element": "option",
                                "attributes": {
                                    "value": "A2",
                                    "label": "Choice A2"
                                }
                            }
                        ]
                    },
                    {
                        "element": "optgroup",
                        "attributes": {
                            "label": "Group B"
                        },
                        "children": [
                            {
                                "element": "option",
                                "attributes": {
                                    "value": "B",
                                    "label": "Choice B"
                                }
                            }
                        ]
                    }
              ]
            },
            {
                "element": "input",
                "attributes": {
                    "name": "cv",
                    "required": "required",
                    "type": "file",
                    "accept": "application/pdf"
                }
            },
            {
                "element": "input",
                "attributes": {
                    "name": "cover_letter",
                    "type": "file",
                    "accept": "application/pdf",
                    "data-max-file-size": "5000000"
                }
            },
            {
                "element": "input",
                "attributes": {
                    "name": "vacancy_id",
                    "type": "hidden"
                }
            },
            {
                "element": "textarea",
                "attributes": {
                    "name": "presentation",
                    "rows": "5",
                    "cols": "10"
                }
            },
            {
                "element": "input",
                "attributes": {
                    "name": "ga_user_id",
                    "type": "hidden"
                }
            }
            ]
        },
        {
            ...
        }
    ]
}
```

