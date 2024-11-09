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
  --data '{
            "resourceType":"Patient",
            "text":{
              "status":"generated",
              "div":"<div xmlns=\"http://www.w3.org/1999/xhtml\"><p style=\"border: 1px #661aff solid; background-color: #e6e6ff; padding: 10px;\"><b>LUCAS HENDRICKX </b> (no stated gender), DoB Unknown ( Internal Identifier:\u00a0AB60001)</p><hr/><table class=\"grid\"><tr><td style=\"background-color: #f3f5da\" title=\"Record is active\">Active:</td><td colspan=\"3\">true</td></tr></table></div>"
            },
            "identifier":[
              {
                "type":{
                  "text":"Internal Identifier"
                },
                "value":"AB60001"
              }
            ],
            "active":true,
            "name":[
              {
                "family":"HENDRICKX",
                "given":["LUCAS"]
              }
            ]
          }'
```



