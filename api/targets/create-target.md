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
IPv4, URL, or Fully Qualified Domain Name, eg. `123.456.789.1`, `google.com`, or `https://google.com/path`
{% endapi-method-parameter %}

{% api-method-parameter name="label" type="string" required=false %}
Label for the target
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=false %}
Up to 10 tags for filtering and sorting
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

