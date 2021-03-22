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

When you register an endpoint, HostedScan creates a signing secret for that endpoint. HostedScan uses this secret to send a signature in the header of each Event message. `X-HOSTEDSCAN-SIGNATURE`. To verify that an event was sent by HostedScan, your application can use the signing secret to recreate a signature for the message and verify that it matches the signature sent in the header.

### Validate the Webhook Signature

The `X-HOSTEDSCAN-SIGNATURE` is a hash-based message authentication code \(HMAC\) generated with SHA-256. To recreate this signature:

1. Prepare the data to be signed. The data is: the message timestamp \(sent in the `X-HOSTEDSCAN-TIMESTAMP` header\), the character `.` ,  and the JSON payload sent in the request body.
2. Compute the expected signature. HMAC with SHA256.
3. Compare the signature your application computed to ensure it matches the value sent in the `X-HOSTEDSCAN-SIGNATURE` header.



{% hint style="info" %}
Any questions? Please email us at [hello@hostedscan.com](mailto:hello@hostedscan.com).
{% endhint %}

