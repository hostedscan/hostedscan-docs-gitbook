# Webhooks

HostedScan uses webhooks to send event notifications to your application. To use webhooks, create a webhook endpoint on your server, then register the endpoint with your HostedScan account.

## Events

The webhook notifications sent by HostedScan are Event objects. An Event is a JSON structure with the following properties: a unique **id**, the **created\_at** time, the event **type,** and the **data**. 

```text
{
  "id": "12345",
  "created_at": 1602918350,
  "type": "scan.completed",
  "data": {
    ...
  }
}
```

### scan.completed

Occurs whenever a scan has completed running. The event data is a Scan object.

```text
{
  "id": "string",
  "type": "NMAP || OPENVAS || OWASP_ZAP",
  "state": SUCCEEDED || FAILED",
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
```

### risk.opened

Occurs whenever a new risk is found. The event data is a Risk object.

```text
{
  "id": "string",
  "target_id": "string",
  "risk_definition": {
    "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
    "title": "string",
    "threat_level": "LOW || MEDIUM || HIGH",
    "additional_info": {
      "key": "value"
    }
  }
}
```

### risk.closed

Occurs when a risk is no longer found to be open. The event data is a Risk object.

```text
{
  "id": "string",
  "target_id": "string",
  "risk_definition": {
    "scan_type": "NMAP || OPENVAS || OWASP_ZAP",
    "title": "string",
    "threat_level": "LOW || MEDIUM || HIGH",
    "additional_info": {
      "key": "value"
    }
  }
}
```

