# Update Target

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/targets/:id" method="put" summary="Update Target" expanded="true" %}
{% swagger-description %}
Update label or tags of an existing target.
{% endswagger-description %}

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
curl -H "Content-Type: application/json" -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request PUT --data '{"label":"Updated Label", "tags":["updated-tag"]}' https://api.hostedscan.com/v1/targets/12345
```
