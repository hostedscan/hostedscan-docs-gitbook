# List Targets

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/targets" %}
{% api-method-summary %}
List Targets
{% endapi-method-summary %}

{% api-method-description %}
List all targets
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="page\_token" type="string" required=false %}
Request a specific page of the list results.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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
      "target": "string",
      "label": "string",
      "tags": [
        "string"
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
