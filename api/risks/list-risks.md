# List Risks

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/risks" %}
{% api-method-summary %}
List Risks
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="target\_id" type="string" required=false %}
Filter list of results to a specific target.
{% endapi-method-parameter %}

{% api-method-parameter name="page\_token" type="string" required=false %}
Request a specific page of the list results.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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



