# Overview

HostedScan uses webhooks to send event notifications to your application. Webhooks are currently available in beta. Please contact us at hello@hostedscan.com for beta access.

## Events

The webhook notifications sent by HostedScan are Event objects. An Event is a JSON structure with the following properties: the event `id`, the `created_at` ****time, the event `type`**,** and the `data`. 

```javascript
{
  "id": "12345",
  "created_at": 1602918350,
  "type": "scan.completed",
  "data": {
    ...
  }
}
```

## Registering an Endpoint

Your webhook endpoint must use HTTPS with a signed certificate, such as one from [https://letsencrypt.org](https://letsencrypt.org). HostedScan will not send to endpoints using self-signed certificates.

## Securing Your Webhooks

When you register an endpoint, HostedScan creates a secret token for that endpoint. HostedScan sends this token in the header of each Event request as `X-HOSTEDSCAN-WH-TOKEN`. To validate that an event was sent by HostedScan, check that the token in the request matches the secret token for your endpoint.



{% hint style="info" %}
Any questions? Please email us at [hello@hostedscan.com](mailto:hello@hostedscan.com).
{% endhint %}

