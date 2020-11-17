# Get Targets

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/targets" %}
{% api-method-summary %}
Get Targets
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="target" type="string" required=false %}
Filter results to a specific target. E.g. /targets?target=example.com
{% endapi-method-parameter %}

{% api-method-parameter name="page\_token" type="string" required=false %}
Request a specific page of the list results.
{% endapi-method-parameter %}

{% api-method-parameter name="page\_size" type="string" required=false %}
The number of results returned in a page. Default = 25. Max = 500.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/targets/:id" %}
{% api-method-summary %}
Get Target
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the target to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "data": {
    "id": "string",
    "target": "string",
    "label": "string",
    "tags": [
      "string"
    ]
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

