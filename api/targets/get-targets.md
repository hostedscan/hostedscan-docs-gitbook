# Get Targets

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/targets" method="get" summary="Get Targets" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="page_token" type="string" %}
If there are more than 500 targets, results will be truncated. Use 

`page_token`

 to request additional pages of results.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
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
{% endswagger-response %}
{% endswagger %}

### Example of listing targets



```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/targets
```

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/targets/:id" method="get" summary="Get Target" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the target to get.
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

### Example of getting a specific target

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/targets/12345
```
