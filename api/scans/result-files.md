# Get Scan Result File

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/results/:id" method="get" summary="Get Scan Result File" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the result file to get.
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns the scan result file" %}
```javascript
// file
```
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -o result.pdf -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET "https://api.hostedscan.com/v1/results/12345"
```

