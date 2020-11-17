# Get Scan Result File

{% api-method method="get" host="https://api.hostedscan.com" path="/v1/scans/results/:id" %}
{% api-method-summary %}
Get Scan Result File
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the result file to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns the scan result file
{% endapi-method-response-example-description %}

```javascript
// file
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Try it!

```bash
curl -o result.pdf -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET "https://api.hostedscan.com/v1/scans/results/12345"
```



