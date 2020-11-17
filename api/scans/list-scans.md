# List Scans

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/scans" %}
{% api-method-summary %}
List Scans
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="page\_size" type="string" required=false %}
Control the number of results returned in a page. Default = 25. Max = 500.
{% endapi-method-parameter %}

{% api-method-parameter name="page\_token" type="string" required=false %}
Request a specific page of the list results.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
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
  next_page_token: "string"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



