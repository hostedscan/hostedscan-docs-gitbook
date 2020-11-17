# Get Targets

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/targets" %}
{% api-method-summary %}
Get Targets
{% endapi-method-summary %}

{% api-method-description %}
Get all targets.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="filters" type="object" required=false %}
Filter results to specific targets, eg. `filters={"tags":["prod"],"target":["hostedscan.com"]}`
{% endapi-method-parameter %}

{% api-method-parameter name="page\_token" type="string" required=false %}
If there are more than 500 targets, results will be truncated. Use `page_token` to request additional pages of results.
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
Get a single target.
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

```javascript
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

