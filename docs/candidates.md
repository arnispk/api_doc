---
layout:default
---

# Candidates

## Create a candidate
***Request***:
```
POST /v1/candidates
```
### Post parameters
| Name | Type | Required | Description | Example |
|---|---|---|---|---|
| vacancy_id | uuid | yes | The job vacancy ID the candidate is applying to. | 0006047b-17e0-492c-a448-caae462dbf8d |
| first_name | string | yes | The candidate first name. | John |
| last_name | string | yes | The candidate last name. | Doe |
| email | email | yes | The candidate email address. | johon.doe@acme.com |
| phone | string | no | The candidate phone number | +31 612 548 745 |
| cv | object | no | The candidate cv object | |
| cv:name | string | no | The name of the cv file being uploaded that must be passed to the ATS if possible | |
| cv:content | string | no | The content of the cv file being uploaded encoded in base64 | |
| cover_letter | object | no | The candidate motivation letter object | |
| cover_letter:name | string | no | The name of the cover letter file being uploaded that must be passed to the ATS if possible | |
| cover_letter:content | string | no | The content of the cover letter file being uploaded encoded in base64 | |
| ga_user_id | string | no | The google analytics user id. | 1124 |

### Response
```json
{
    "code": "202",
    "message": "candidate was accepted.",
    "description": "The resource was accepted and will now be processed.",
    "data": {
        "id": "b72262d6-26e8-4130-b25c-11e46effa269",
        "creationDate": "2000-01-01 00:00:00"
    }
}
```
