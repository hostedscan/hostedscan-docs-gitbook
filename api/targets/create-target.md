# Create Target

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/targets" method="post" summary="Create Target" expanded="true" %}
{% swagger-description %}
 
{% endswagger-description %}

{% swagger-parameter in="query" name="upsert" type="boolean" %}
Update target if it already exists. Defaults to false.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="target" type="string" %}
IPv4, URL, or Fully Qualified Domain Name, eg. 

`123.456.789.1`

, 

`google.com`

, or 

`https://google.com/path`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="label" type="string" %}
Label for the target
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="array" %}
Up to 10 tags for filtering and sorting
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
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
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -H "Content-Type: application/json" -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request POST --data '{"target":"test.com", "tags":["api-test"]}' https://api.hostedscan.com/v1/targets
```
