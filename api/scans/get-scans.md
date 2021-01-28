# Get Scans

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/scans" %}
{% api-method-summary %}
Get Scans
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="filters" type="object" required=false %}
Filter results to specific scans. e.g. `filters={"type":["NMAP"],"state":["SUCCEEDED"]}`
{% endapi-method-parameter %}

{% api-method-parameter name="page\_token" type="string" required=false %}
If there are more than 500 scans, results will be truncated. Use `page_token` to request additional pages of results.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "data": [
    {
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
  ],
  "next_page_token": "string"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/scans
```

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/scans/:id" %}
{% api-method-summary %}
Get Scan
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the scan to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
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
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/scans/12345
```

