# Get Risks

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/risks" method="get" summary="Get Risks" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="page_token" type="string" %}
If there are more than 500 risks, results will be truncated. Use 

`page_token`

 to request additional pages of results.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="filters" type="object" %}
Key value pairs of filters, where each value is an array to filter on. E.g.



`{"risk_definition.scantype": ['NMAP', 'NMAP_UDP']}`



Allowed keys: `target_id, status, tags, risk_definition.scan_type, risk_definition.threat_level, risk_definition.title`


{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "data": [
    {
      "id": "string",
      "target_id": "string",
      "target": "string",
      "target_label": "string",
      "tags": [],
      "status": "OPEN || CLOSED",
      "is_accepted": boolean,
      "accepted_by": [
        {
          "note": "string",
          "created_at": "Date",
          "last_updated_at": "Date"
        }
      ],
      "risk_definition": {
        "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
        "title": "string",
        "threat_level": "LOW || MEDIUM || HIGH",
        "additional_info": {
          "key": "value"
        },
        "first_detected_at": "Date",
        "last_detected_at": "Date"
      }
    }
  ],
  next_page_token: "string"
}
```
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/risks
```

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/risks/:id" method="get" summary="Get Risk" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" required="true" %}
ID of the risk to get.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    {
      "id": "string",
      "target_id": "string",
      "target": "string",
      "target_label": "string",
      "tags": [],
      "status": "OPEN || CLOSED",
      "is_accepted": boolean,
      "accepted_by": [
        {
          "note": "string",
          "created_at": "Date",
          "last_updated_at": "Date"
        }
      ],
      "risk_definition": {
        "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
        "title": "string",
        "threat_level": "LOW || MEDIUM || HIGH",
        "additional_info": {
          "key": "value"
        }
      },
      "first_detected_at": "Date",
      "last_detected_at": "Date"
    }
  }
}
```
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/risks/12345
```
