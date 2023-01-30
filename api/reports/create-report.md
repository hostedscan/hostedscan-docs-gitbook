# Create Report



{% swagger method="post" path="" baseUrl="https://api.hostedscan.com/v1/report" summary="Create Report" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="report_format" required="true" %}
"PDF" or "HTML"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="targets_filter" type="Object" %}
Array of target ids or tags. 

`{ id: ["target-123"] }`

 of { 

`tag: ["example-tag"] }`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="risks_filter" type="Object" %}
Key value pairs of filters, where each value is an array to filter on. E.g.



`{"risk_definition.scantype": ['NMAP', 'NMAP_UDP']}`



Allowed keys: `status, risk_definition.scan_type, risk_definition.threat_level, risk_definition.title`
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "data": {
        "id": "example-key-123" // Id to GET the report file
    }
}
```
{% endswagger-response %}
{% endswagger %}
