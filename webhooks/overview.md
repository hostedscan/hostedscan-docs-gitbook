# Overview

HostedScan uses webhooks to send event notifications to your application. Webhooks are available to Enterprise plan customers.

## Events

The webhook notifications sent by HostedScan are Event objects. An Event is a JSON structure with the following properties: a unique `id`, the `created_at` ****time, the event `type`**,** and the `data`. 

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



