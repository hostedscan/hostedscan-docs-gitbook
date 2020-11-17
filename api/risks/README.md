# Risks

Risks are the findings from scans. For example, a vulnerable javascript dependency or an open port.

### Risk Object

```text
{
  "id": "string",
  "target_id": "string",
  "status": "OPEN || CLOSED",
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

