# Create Scan

{% api-method method="post" host="https://api.hostedscan.com" path="/v1/scans" %}
{% api-method-summary %}
Create Scan
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="targets" type="array" required=false %}
Targets to scan. e.g. `["example.com", "123.123.123.123"]`  Either targets or target\_ids must be specified.
{% endapi-method-parameter %}

{% api-method-parameter name="target\_ids" type="array" required=false %}
IDs of targets to scan. Either targets or target\_ids must be specified.
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
NMAP, NMAP\_UDP, SSLYZE, OPENVAS, or OWASP\_ZAP
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Try it!

```bash
curl -H "Content-Type: application/json" -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request POST --data '{"target_ids": ["123", "456"], "type": "NMAP"}' https://api.hostedscan.com/v1/scans
```

