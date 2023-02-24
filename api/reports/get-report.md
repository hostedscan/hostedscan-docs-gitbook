---
description: Download vulnerability report files.
---

# Get Report

{% swagger method="get" path="" baseUrl="https://api.hostedscan.com/reports/:id" summary="Download a report" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" required="true" name="id" %}
ID of the report to get
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // File
}
```
{% endswagger-response %}
{% endswagger %}

## Example of downloading a report

```shell
curl --header "X-HOSTEDSCAN-API-KEY: your-api-key-here" \
     --request GET \
     --output report.pdf \
     https://api.hostedscan.com/v1/reports/id-of-created-report-here
```
