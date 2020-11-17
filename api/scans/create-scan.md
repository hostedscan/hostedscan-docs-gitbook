# Create Scan

{% api-method method="post" host="https://api.hostedscan.com" path="/v1/scans" %}
{% api-method-summary %}
Create Scan
{% endapi-method-summary %}

{% api-method-description %}
Create a new scan.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="target\_ids" type="array" required=true %}
Ids of targets to scan
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
NMAP, OPENVAS, or OWASP\_ZAP
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
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



