# Overview

HostedScan uses webhooks to send event notifications to your application. Receive events when scans finish or when new risks are discovered.

## Events

The webhook notifications sent by HostedScan are Event objects. An Event is a JSON structure with the following properties: the event `id`, the `created_at` time, the event `type`**,** and the `data`.&#x20;

```javascript
{
  "id": "12345",
  "created_at": 1602918350,
  "type": "scan.succeeded",
  "data": {
    ...
  }
}
```

{% content-ref url="event-types.md" %}
[event-types.md](event-types.md)
{% endcontent-ref %}

## Registering an Endpoint

Your webhook endpoint must use HTTPS with a signed certificate, such as one from [https://letsencrypt.org](https://letsencrypt.org). HostedScan will not send to endpoints using self-signed certificates.

You can register new webhook endpoints and view your existing webhook endpoints in your account settings at [https://hostedscan.com/settings](https://hostedscan.com/settings).

<figure><img src="../.gitbook/assets/Screenshot 2023-02-23 at 4.13.20 PM.png" alt=""><figcaption><p>Register new endpoints. view logs, and find the endpoint signing secret at <a href="https://hostedscan.com/settings">https://hostedscan.com/settings</a></p></figcaption></figure>

## Message Delivery and Retries

HostedScan will attempt to deliver messages to your endpoint for up to 12 hours, with exponential backoff. Any 2xx response code from your endpoint is treated as a successful delivery. Any non-2xx status code (or a timeout) is treated as a failure and will be retried.&#x20;

## Securing Your Webhooks

When you register an endpoint, HostedScan creates a signing secret for that endpoint. HostedScan uses this secret to send a signature in the header of each Event message. The signature can be validated using the signing secret to verify that an event was sent by HostedScan.

### Validate the Webhook Signature

Each webhook message request includes an http header X`-HOSTEDSCAN-SIGNATURE`. The `X-HOSTEDSCAN-SIGNATURE` is a hash-based message authentication code (HMAC) generated with SHA-256. To validate this signature an application will first recreate the signature using the signing secret for that endpoint and then check that the signature sent in the `X-HOSTEDSCAN-SIGNATURE` header matches the recreated signature. To do this, follow the steps below:

1. Prepare the data to be signed. The data is: the message timestamp (sent in the `X-HOSTEDSCAN-TIMESTAMP` header), the character . , and the JSON payload sent in the request body.
2. Compute the expected signature. HMAC with SHA256.
3. Compare the signature your application computed to ensure it matches the value sent in the `X-HOSTEDSCAN-SIGNATURE` header.

## Sample Code

The hostedscan-api-examples Github repository has sample code for receiving webhooks with an AWS Lambda function.

{% embed url="https://github.com/hostedscan/hostedscan-api-examples/tree/main/receive_webhooks_with_aws_lambda/rust" %}



{% hint style="info" %}
Any questions? Please email us at [hello@hostedscan.com](mailto:hello@hostedscan.com).
{% endhint %}
