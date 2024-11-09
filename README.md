## Overview

 - [Styling](https://github.com/pages-themes/cayman)
 - [Public Test Servers](https://confluence.hl7.org/display/FHIR/Public+Test+Servers)
 - [FHIR](https://hl7.org/fhir/)
 - [REST API](https://hl7.org/fhir/http.html)
 - [Online Postman](https://web.postman.co/)

## Current Guide

 - [Youtube](https://www.youtube.com/watch?v=m2O6HiA1Z7g&list=PLsR-zcO--dypUxuALrmuq70aM-VGX_ql1&index=1)
 - [GitHub](https://github.com/GinoCanessa)

---

## First Requests

### GET Metadata of Server

```cURL
curl \
  --location 'http://hapi.fhir.org/baseR5/metadata' \
  --header 'Accept: application/fhir+json'
```


### GET All Patients

```cURL
curl \
  --location 'http://hapi.fhir.org/baseR5/Patient' \
  --header 'Accept: application/fhir+json'
```

### GET Specific Patient

```cURL
curl \
  --location 'http://hapi.fhir.org/baseR5/Patient/787004' \
  --header 'Accept: application/fhir+json'
```


### POST new Patient

```cURL
curl \
  --location 'http://hapi.fhir.org/baseR5/Patient' \
  --header 'Accept: application/fhir+json' \
  --header 'Content-Type: application/fhir+json' \
  --data '{SEE JSON BELOW}'
```
```json
{
    "resourceType": "Patient",

--- RESPONSE PART --------------------------------------------------------------------------

    "id": "787005",
    "meta": {
        "versionId": "1",
        "lastUpdated": "2024-11-09T18:01:43.203+00:00",
        "source": "#X4umTNF23WGJAGgA"
    },
    "text": {
        "status": "generated",
        "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\"><div class=\"hapiHeaderText\">John <b>DOE </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>123-45-6789</td></tr><tr><td>Address</td><td><span>123 Main Street </span><br/><span>Brussels </span><span>Belgium </span></td></tr><tr><td>Date of birth</td><td><span>15 May 1985</span></td></tr></tbody></table></div>"
    },

--------------------------------------------------------------------------------------------

    "identifier": [
        {
            "use": "official",
            "type": {
                "coding": [
                    {
                        "system": "http://terminology.hl7.org/CodeSystem/v2-0203",
                        "code": "SS",
                        "display": "Social Security Number"
                    }
                ]
            },
            "system": "urn:oid:2.16.840.1.113883.2.4.6.3",
            "value": "123-45-6789"
        }
    ],
    "active": true,
    "name": [
        {
            "use": "official",
            "family": "Doe",
            "given": [
                "John"
            ]
        }
    ],
    "telecom": [
        {
            "system": "phone",
            "value": "+32 2 123 45 67",
            "use": "home"
        },
        {
            "system": "email",
            "value": "johndoe@example.com",
            "use": "home"
        }
    ],
    "gender": "male",
    "birthDate": "1985-05-15",
    "address": [
        {
            "use": "home",
            "line": [
                "123 Main Street"
            ],
            "city": "Brussels",
            "postalCode": "1000",
            "country": "Belgium"
        }
    ],
    "maritalStatus": {
        "coding": [
            {
                "system": "http://terminology.hl7.org/CodeSystem/v3-MaritalStatus",
                "code": "S",
                "display": "Single"
            }
        ]
    },
    "communication": [
        {
            "language": {
                "coding": [
                    {
                        "system": "urn:ietf:bcp:47",
                        "code": "nl",
                        "display": "Dutch"
                    }
                ]
            },
            "preferred": true
        }
    ]
}
```


