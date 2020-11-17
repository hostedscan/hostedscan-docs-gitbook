---
description: 'Run OpenVAS scanner, NMAP Port Scan, and OWASP ZAP against your Targets.'
---

# Scans

### Scan Object

```javascript
{
  "id": "string",
  "type": "NMAP || OPENVAS || OWASP_ZAP",
  "state": "QUEUED || RUNNING || SUCCEEDED || FAILED || OVER_LIMIT",
  "progress": 100,
  "results": [
    {
      "result_id": "string",
      "content_type": "text/html"
    },
    {
      "result_id": "string",
      "content_type": "application/pdf"
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
```

