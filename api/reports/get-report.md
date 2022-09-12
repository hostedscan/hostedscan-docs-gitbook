---
description: Download vulnerability report files.
---

# Get Report

{% swagger method="get" path="" baseUrl="https://api.hostedscan.com/reports/:id" summary="Download a report" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" required="true" %}
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
