# Create Scan

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/scans" method="post" summary="Create Scan" %}
{% swagger-description %}
Run a new vulnerability scan. Scan is created in the QUEUED state and will transition to RUNNING while it is in progress and then to SUCCEEDED once it is finished.
{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" required="true" %}
NMAP, NMAP_UDP, SSLYZE, OPENVAS, or OWASP_ZAP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="targets" type="array" %}
Targets to scan. e.g. 

`["example.com", "123.123.123.123"]`

 Either tags, targets, or target_ids must be specified.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="target_ids" type="array" %}
IDs of targets to scan. Either tags, targets, or target_ids must be specified.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="array" required="false" %}
Tags to scan. e.g. 

`["prod", "webserver"]`

 Either tags, targets, or target_ids must be specified.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="use_authentication" type="boolean" %}
Use authentication, if configured for the target(s). See 

[https://hostedscan.com/authenticated-web-app-vulnerability-scan](https://hostedscan.com/authenticated-web-app-vulnerability-scan)

 for more details.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "data": {
    "id": "string",
    "type": "NMAP || OPENVAS || OWASP_ZAP",
    "state": "QUEUED || RUNNING || SUCCEEDED || FAILED || OVER_LIMIT",
    "progress": 100,
    "results": [
      {
        "result_id": "string",
        "content_type": "text/html"
      },
      {
        "result_id": "string",
        "content_type": "application/pdf"
      }
    ],
    "requested_targets": [
      {
        "target_id": "string",
        "target": "string"
      }
    ],
    "resolved_targets": [
      {
        "target_id": "string",
        "resolved_target": "string"
      }
    ],
    "skipped_targets": [
      {
        "target_id": "string",
        "skipped_reason": "string"
      }
    ]
  }
}
```
{% endswagger-response %}
{% endswagger %}

## Try it!

```bash
curl -H "Content-Type: application/json" -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request POST --data '{"target_ids": ["123", "456"], "type": "NMAP"}' https://api.hostedscan.com/v1/scans
```
