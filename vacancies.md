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

```
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
                        "linkedIn": "https://www.linkedin.com/in/batman-bruce-wayne-43275131"
                    },
                    "picture-link": "https://www.imagedepot.com/usr/1290395.png",
                    "picture-data": "QW4gaW1hZ2UgZGF0YSB3aWxsIGJlIGVuY29kZWQgaGVyZSBpbiBiYXNlIDY0IGZvcm1hdA==",
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
            "applicationFormUrl": "http://www.acmeats.com/job-application-iframe/55543-2213",
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

#### Table of Reference
