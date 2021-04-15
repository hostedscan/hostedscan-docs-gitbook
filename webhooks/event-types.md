---
description: The list of all event types HostedScan currently sends.
---

# Event Types

### scan.succeeded

Occurs whenever a scan has successfully completed running. The event data is a Scan object.

```javascript
{
  "data": {
    "id": "string",
    "type": "NMAP || OPENVAS || OWASP_ZAP",
    "state": "SUCCEEDED",
    "progress": 100,
    "results": [
      {
        "result_id": "string",
        "content_type": "text/html"
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

### risk.opened

Occurs whenever a new risk is found. The event data is a Risk objects.

```javascript
{
  "data": {
    "id": "string",
    "target_id": "string",
    "target": "string",
    "tags": [],
    "status": "OPEN",
    "risk_definition": {
      "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
      "title": "string",
      "threat_level": "LOW || MEDIUM || HIGH",
      "additional_info": {
        "key": "value"
      }
    }
  }
}
```

### risk.closed

Occurs when a risk is no longer found to be open. The event data is a Risk object.

```javascript
{
  "data": {
    "id": "string",
    "target_id": "string",
    "target": "string",
    "tags": [],
    "status": "CLOSED",
    "risk_definition": {
      "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
      "title": "string",
      "threat_level": "LOW || MEDIUM || HIGH",
      "additional_info": {
        "key": "value"
      }
    }
  }
}
```

