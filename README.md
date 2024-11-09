## Overview

 - [Styling](https://github.com/pages-themes/cayman)
 - [Public Test Servers](https://confluence.hl7.org/display/FHIR/Public+Test+Servers)
 - [FHIR](https://hl7.org/fhir/)
 - [REST API](https://hl7.org/fhir/http.html)
 - [Online Postman](https://web.postman.co/)

## Current Guide

 - [Youtube]([https://github.com/GinoCanessa](https://www.youtube.com/watch?v=m2O6HiA1Z7g&list=PLsR-zcO--dypUxuALrmuq70aM-VGX_ql1&index=1))
 - [GitHub](https://github.com/GinoCanessa)

---

## First Requests

### Get Metadata of Server

```C#
var client = new HttpClient();
var request = new HttpRequestMessage(HttpMethod.Get, "http://hapi.fhir.org/baseR5/metadata");
request.Headers.Add("Accept", "application/fhir+json");
var response = await client.SendAsync(request);
response.EnsureSuccessStatusCode();
Console.WriteLine(await response.Content.ReadAsStringAsync());
```

