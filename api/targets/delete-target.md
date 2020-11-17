# Delete Target

{% api-method method="delete" host="https://api.hostedscan.com" path="/v1/targets/:id" %}
{% api-method-summary %}
Delete Target
{% endapi-method-summary %}

{% api-method-description %}
Note: Deleting a target will also delete any risks associated with that target.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the target to delete.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns 200 OK with an empty body
{% endapi-method-response-example-description %}

```javascript
// N/A
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request DELETE https://api.hostedscan.com/v1/targets/12345
```

