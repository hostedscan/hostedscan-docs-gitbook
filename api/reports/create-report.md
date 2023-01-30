---
description: Create a report for download
---

# Create Report



{% swagger method="post" path="" baseUrl="https://api.hostedscan.com/v1/reports" summary="Create Report" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="report_format" required="true" %}
`PDF`

 or 

`HTML`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="targets_filter" type="Object" %}
Array of target ids or tags. 

`{ "target_ids": ["target-123"] }`

 of { 

`"tag": ["example-tag"] }`
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

## Example of creating a basic report

```shell
curl --header "X-HOSTEDSCAN-API-KEY: your-api-key-here" \
     --header "Content-Type: application/json" \
     --request POST \
     --data '{"report_format": "PDF"}' \
     https://api.hostedscan.com/v1/reports
```

## Example of creating a filtered report

```shell
curl --header "X-HOSTEDSCAN-API-KEY: your-api-key-here" \
     --header "Content-Type: application/json" \
     --request POST \
     --data '{ "report_format": "PDF", "risks_filter": { "target.target": ["255.255.target-ip-here"] }, "targets_filter": { "target_ids": ["1a2b3c-target-id-here"] } }' \
     https://api.hostedscan.com/v1/reports
```
