---
layout: default
---

[Home](index)

# Vacancies

## Retrieve all Vacancies

***Request***:

```
GET /v1/vacancies
```

### Query Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| limit | number | no | Limit the number of results returned by the API. |
| offset | number | no | Sets the record from which results are returned. Usually used with the Limit clause.  |
| output | string | no | The type of output to provide. Available options are 'json' and 'custom'. Defaults to JSON. |
| status | string | no | The vacancy status to return. Available options are 'scheduled', 'open', 'on-hold', 'closed'. If not specified every vacancy is returned. |

## Retrieve one Vacancy by ID

***Request***:
```
GET /v1/vacancies/{id}
```

### Query Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| id | uuid | yes | The id of the record to return from the API. |

### Response

```json
{
    "nextUpdate": "2016-05-16 12:15:02",
    "timeZoneId": "UTC",
    "totalFound": "2",
    "data": [
        {
            "id": "b72262d6-26e8-4130-b25c-11e46effa269",
            "provider": "Whires",
            "externalID": "55543-2213",
            "refNumber": "SRDEV102",
            "status": "open",
            "title": "Senior PHP Developer - Amsterdam",
            "language": "en-US",
            "descriptions": [
                {
                    "channel": "default",
                    "title": "Senior PHP Developer - Amsterdam",
                    "company": "We are a new company focused in making trouble.",
                    "summary": "Senior PHP Dev",
                    "role": "We are looking for a new Senior PHP Developer.",
                    "requirements": "",
                    "benefits": "",
                    "additionalInformation": "",
                    "startDate": "2016-10-12 01:00:00",
                    "endDate": null
                }
            ],
            "departments": [
                {
                    "id": "human-resources",
                    "name": "Human Resources"
                },
                {
                    "id": "information-technology",
                    "name": "Information Technology"
                }
            ],
            "contractTypes": [],
            "jobTypes": [
                {
                    "id": "fullTime",
                    "name": "Full-Time"
                }
            ],
            "experienceLevels": [
                {
                    "id": "senior-level",
                    "name": "Senior"
                }
            ],
            "educationLevels": [
                {
                    "id": "mbo",
                    "name": "MBO"
                }
            ],
            "functions": [
                {
                    "id": 3,
                    "name": "HR"
                },
                {
                    "id": 4,
                    "name": "IT Development"
                }
            ],
            "positionLevels": [
                {
                    "id": 203,
                    "name": "Senior"
                }
            ],
            "hoursPerWeek": [
                {
                    "id": "40",
                    "name": "40"
                }
            ],
            "salary": {    
                "value": null,
                "range": {
                    "min": 10000,
                    "max": 20000
                },
                "currency": "EUR",
                "currencySymbol": "€",
                "period": "month",
                "isGross": true
            },
            "company": {
                "id": "34254",
                "name": "Endouble BV"
            },
            "locations": [
                {
                    "id": "ABCD1234",
                    "name": "AMS 1 - Headquarters",
                    "address": "Asterweg 20 K1",
                    "zipCode": "1031HL",
                    "city": "Amsterdam",
                    "region": "North Holland",
                    "regionCode": "NL-NH",
                    "country": "Netherlands",
                    "countryCode": "NL",
                    "latitude": "52.37020380000001",
                    "longitude": "4.89532650000001"
                }
            ],
            "recruiters": [
                {
                    "id": null,
                    "name": "Mary Jane",
                    "email": "mary.jane@acme.com",
                    "phone": "919212775",
                    "links": {
                        "facebook": null,
                        "twitter": "https://twitter.com/official_php",
                        "linkedIn": "https://www.linkedin.com/in/batman-bruce-wayne-75131"
                    },
                    "picture-link": "https://www.imagedepot.com/usr/1290395.png",
                    "picture-data": "WxsIGJlIGVuY29kZWQgaGVyZSBpbiBiYXNlIDY0IGZvcm1hdA==",
                },
                {
                    "name": "John Doe",
                    "email": "john.doe@acme.com",
                    "phone": null,
                    "links": {},
                    "picture-link": null,
                    "picture-data": null,
                }
            ],
            "markers": {
                "isInternal": false,
                "isFeatured": true
            },
            "applicationFormUrl": "http://www.acmeats.com/job-application/55543-2213",
            "creationDate": "2016-05-11 15:06:12",
            "updateDate": "2016-05-13 12:08:22",
            "startDate": "2016-05-15 00:00:00",
            "endDate": "2016-06-25 00:00:00"
        },
        {
            ...
        }
    ]
}
```

### Table of Reference

| Name | Type | Description |
|---|---|---|
| nextUpdate | dateTime\|null | The date resources will be updated and retrieved from the external ATS. |
| timeZoneId | string | The current timezone ID ([php.net:timezones](http://php.net/manual/en/timezones.php)) |
| totalFound | int | The total amount of available vacancies. |
| data:id | uuid | The ATS Central vacancy ID. |
| data:provider | string | The external ATS name reference |
| data:externalID | string | The external ATS vacancy ID |
| data:refNumber | string\|null | The external ATS vacancy reference number. |
| data:title | string\|null | The vacancy main title. |
| data:language | string\|null | The vacancy language code. |
| data:descriptions | array | Holds all the vacancy channel description sections. |
| data:descriptions:title | string\|null | The vacancy title for this channel. |
| data:descriptions:channel | string | The description channel name. Possible values are:<br>*   **default** - The default description section (can be used by career websites, others);<br>*   **facebook** - The Facebook related descriptions channel;<br>*   **twitter** - The Twitter related descriptions channel;<br>If the remote ATS doesn't specify a channel, the "**default**" option will be used. |
| data:descriptions:company | string\|null | The vacancy related description about the company. |
| data:descriptions:summary | string\|null | A summary of the vacancy |
| data:descriptions:role | string\|null | The vacancy main description. |
| data:descriptions:requirements | string\|null | The vacancy description about required qualifications. |
| data:descriptions:benefits | string\|null | The vacancy description about provided benefits. |
| data:descriptions:additionalInformation | string\|null | Additional description. |
| data:descriptions:startDate | dateTime\|null | The date this description channel should be published. |
| data:descriptions:endDate | dateTime\|null | The date this description channel should be unpublished. |
data:departments | array | The department. |
| data:departments:id | string\|null | The department ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:departments:name | string\|null | The department name. If null means that there is no available translation in the vacancy's language for this item |
| data:contractTypes | array | The contract type. |
| data:contractTypes:id | string\|null | The contract type ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:contractTypes:name | string\|null | The contract type name. If null means that there is no available translation in the vacancy's language for this item |
| data:jobTypes | array | The job type. |
| data:jobTypes:id | string\|null | The job type ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:jobTypes:name | string\|null | The job type name. If null means that there is no available translation in the vacancy's language for this item |
| data:experienceLevels | array | The experience level |
| data:experienceLevels:id | string\|null | The experience level ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:experienceLevels:name | string\|null | The experience level name. If null means that there is no available translation in the vacancy's language for this item |
| data:educationLevels | array | The education level |
| data:educationLevels:id | string\|null | The education level ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:educationLevels:name | string\|null | The education level name. If null means that there is no available translation in the vacancy's language for this item |
| data:functions | array | The functions that are related to the position |
| data:functions:id | string\|null | The function id. If null it means that the remote ATS doesn't provide an ID for this item |
| data:functions:name | string\|null | The function name. If null means that there is no available translation in the vacancy's language for this item |
| data:positionLevels | array | The level of the position (this is NOT related to seniority) |
| data:positionLevels:id | string\|null | The level id. If null it means that the remote ATS doesn't provide an ID for this item |
| data:positionLevels:name | string\|null | The level name. If null means that there is no available translation in the vacancy's language for this item |
| data:hoursPerWeek | array | The hours per week. |
| data:hoursPerWeek:id | string\|null | The hours per week ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:hoursPerWeek:name | string\|null | The hours per week name. If null means that there is no available translation in the vacancy's language for this item |
| data:company | object\|empty | The company the vacancy is related to. |
| data:company:id | string\|null | The company ID. If null it means that the remote ATS doesn't provide an ID for this item |
| data:company:name | string\|null | The company name. If null means that there is no available translation in the vacancy's language for this item |
| data:salary | object | Holds salary related details. |
| data:salary:value | string\|null | The salary value in textual description format. This cannot be relied to be a number. |
| data:salary:range:min | int\|null | The minimum salary. |
| data:salary:range:max | int\|null | The maximum salary. |
| data:salary:currency | string\|null | The currency string formatted name. |
| data:salary:currencySymbol | string\|null | The currency symbol. |
| data:salary:period | string\|null | The time recurrence the salary is based in. Possible values are: <br>*   **hour** - Salary value is hourly based.<br>*   **week** - Salary value is weekly based.<br>*   **fortnight** - Salary value is biweekly based.<br>*   **month** - Salary value is monthly based.<br>*   **year** - Salary value is yearly based.<br>*   **one-time** - Salary is fixed and paid only once; |
| data:salary:isGross | bool\|null | Is the salary gross or net? |
| data:locations | array | The vacancy location. |
| data:locations:id | string\|null | The location ID, if provided by the source ATS. Null otherwise |
| data:locations:name | string\|null | The location name, or title. A label that marks the location |
| data:locations:address | string\|null | The location address. |
| data:locations:city | string\|null | The location city. |
| data:locations:region | string\|null | The location region. |
| data:locations:regionCode | string\|null | The location region code. |
| data:locations:country | string\|null | The location country. |
| data:locations:countryCode | string\|null | The location country code. |
| data:locations:latitude | float\|null | The location latitude coordinates. |
| data:locations:longitude | float\|null | The location longitude coordinates. |
| data:recruiters | array | List of recruiters related to the vacancy. |
| data:recruiters:id | string\|null | The recruiter ID if provided by the source ATS. Null otherwise |
| data:recruiters:name | string\|null | The recruiter name. |
| data:recruiters:email | string\|null | The recruiter email address. |
| data:recruiters:phone | string\|null | The recruiter phone number. |
| data:recruiters:links | object\|empty | The recruiter social media links. Each of this object's keys represent a distinct link (for example, facebook, twitter, linkedin). Each link is a nullable string. |
| data:recruiters:picture-link | string\|null | The recruiter's image URL, if available |
| data:recruiters:picture-data | string\|null | The recruiter's image in base64 format, if available |
| data:markers | object | Sets vacancy extra parameters and markers. |
| data:markers:isInternal | bool\|null | Identifies the vacancy as part of an internal sub-list of vacancies. |
| data:markers:isFeatured | bool\|null | Identifies the vacancy as a featured vacancy. |
| data:applicationFormUrl | string\|null | The link to an external application form URL (provided by the External ATS). |
| creationDate | dateTime | The date the resource was created in the ATS Central. |
| updateDate | dateTime | The date the resource was updated in the ATS Central. |
| startDate | dateTime\|null | The date this resource is considered active. |
| endDate | dateTime\|null | The date this resource is considered inactive. |
| status | string | Specifies the status of the vacancy. Possible values are:<br>*   **scheduled** - vacancy is scheduled to be open on a given date;<br>*   **open** - vacancy is active and should be displayed;<br>*   **on-hold** - vacancy put on hold;<br>*   **closed** - vacancy is closed; |

