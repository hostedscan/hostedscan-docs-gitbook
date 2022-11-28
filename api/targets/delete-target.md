# Delete Target

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/targets/:id" method="delete" summary="Delete Target" expanded="true" %}
{% swagger-description %}
Note: Deleting a target will also delete any risks associated with that target.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the target to delete.
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns 200 OK with an empty body" %}
```javascript
// N/A
```
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request DELETE https://api.hostedscan.com/v1/targets/12345
```
