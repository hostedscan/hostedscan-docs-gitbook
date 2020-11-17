# Get Risks

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/risks" %}
{% api-method-summary %}
Get Risks
{% endapi-method-summary %}

{% api-method-description %}
Get all risks.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="filter" type="string" required=false %}
Filter results to specific targets. e.g. `filters={"target":["hostedscan.com"],"risk_definition.scan_type":["NMAP"]}`
{% endapi-method-parameter %}

{% api-method-parameter name="page\_token" type="string" required=false %}
If there are more than 500 risks, results will be truncated. Use `page_token` to request additional pages of results.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
  "data": [
    {
      "id": "string",
      "target_id": "string",
      "status": "OPEN || CLOSED",
      "risk_definition": {
        "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
        "title": "string",
        "threat_level": "LOW || MEDIUM || HIGH",
        "additional_info": {
          "key": "value"
        }
      }
    }
  ],
  next_page_token: "string"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



