# Create Target

{% api-method method="post" host="https://api.hostedscan.com" path="/v1/targets" %}
{% api-method-summary %}
Create Target
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="target" type="string" required=true %}
IPv4, URL, or Fully Qualified Domain Name
{% endapi-method-parameter %}

{% api-method-parameter name="label" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=false %}
Up to 3 tags
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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
