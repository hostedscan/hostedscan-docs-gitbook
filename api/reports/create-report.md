# Create Report



{% swagger method="post" path="" baseUrl="https://api.hostedscan.com/v1/report" summary="Create Report" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="report_format" required="true" %}
"PDF" or "HTML"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="targets_filter" type="Object" %}
Array of target ids or tags. { id: ["target-123"] } of { tag: ["example-tag"] }
{% endswagger-parameter %}

{% swagger-parameter in="body" name="" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "report_id": "example-key-123" // Id to GET the report file
}
```
{% endswagger-response %}
{% endswagger %}
