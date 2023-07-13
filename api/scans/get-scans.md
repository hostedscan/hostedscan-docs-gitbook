# Get Scans

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/scans" method="get" summary="Get Scans" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="page_token" type="string" %}
If there are more than 500 scans, results will be truncated. Use 

`page_token`

 to request additional pages of results.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="filters" type="object" %}
Key value pairs of filters, where each value is an array to filter on. E.g.



`{"state": ["RUNNING"], "type": ["OPENVAS"]}`



Allowed keys: `type, state, scheduled_by`
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "data": [
    {
      "id": "string",
      "type": "NMAP || OPENVAS || OWASP_ZAP || OWASP_ZAP_ACTIVE || SSLYZE",
      "state": "QUEUED || RUNNING || SUCCEEDED || FAILED || OVER_LIMIT",
      "progress": 100,
      "risks": {
        "new_open": [
          {
            "risk_id": "string",
          }
        ],
        "still_open": [
          {
            "risk_id": "string",
          }
        ],
        "closed": [
          {
            "risk_id": "string",
          }
        ]
      },
      "results": [
        {
          "result_id": "string",
          "content_type": "text/html"
        },
        {
          "result_id": "string",
          "content_type": "application/pdf"
        },
        {
          "result_id": "string",
          "content_type": "application/xml"
        },
        {
          "result_id": "string",
          "content_type": "application/json"
        }
      ],
      "requested_targets": [
        {
          "target_id": "string",
          "target": "string"
        }
      ],
      "resolved_targets": [
        {
          "target_id": "string",
          "resolved_target": "string"
        }
      ],
      "skipped_targets": [
        {
          "target_id": "string",
          "skipped_reason": "string"
        }
      ]
    }
  ],
  "next_page_token": "string"
}
```
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/scans
```

### Example of listing scans with filters

```shell
curl -H "X-HOSTEDSCAN-API-KEY: your-api-key" -G --data-urlencode 'filters={"state": ["RUNNING"], "type": ["OPENVAS"]}' https://api.hostedscan.com/v1/scans
```

{% swagger baseUrl="https://api.hostedscan.com" path="/v1/scans/:id" method="get" summary="Get Scan" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" required="true" %}
ID of the scan to get.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "data": {
    "id": "string",
    "type": "NMAP || OPENVAS || OWASP_ZAP || OWASP_ZAP_ACTIVE || SSLYZE",
    "state": "QUEUED || RUNNING || SUCCEEDED || FAILED || OVER_LIMIT",
    "progress": 100,
    "risks": {
      "new_open": [
        {
          "risk_id": "string",
        }
      ],
      "still_open": [
        {
          "risk_id": "string",
        }
      ],
      "closed": [
        {
          "risk_id": "string",
        }
      ]
    },
    "results": [
      {
        "result_id": "string",
        "content_type": "text/html"
      },
      {
        "result_id": "string",
        "content_type": "application/pdf"
      },
      {
        "result_id": "string",
        "content_type": "application/xml"
      },
      {
        "result_id": "string",
        "content_type": "application/json"
      }
    ],
    "requested_targets": [
      {
        "target_id": "string",
        "target": "string"
      }
    ],
    "resolved_targets": [
      {
        "target_id": "string",
        "resolved_target": "string"
      }
    ],
    "skipped_targets": [
      {
        "target_id": "string",
        "skipped_reason": "string"
      }
    ]
  }
}
```
{% endswagger-response %}
{% endswagger %}

### Try it!

```bash
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/scans/12345
```
