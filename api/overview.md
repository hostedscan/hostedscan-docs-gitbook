# Overview

HostedScan offers a comprehensive REST API at https://api.hostedscan.com/v1. API access is available to Enterprise plan customers.

## Authentication

Authenticate by setting the X-HOSTEDSCAN-API-KEY request header as your API key.

## Testing with Sample Data

To try out the APIs with sample data, use the api key **test-data-key**. Requests made with this api key will return sample responses. For example:

```text
curl -H "X-HOSTEDSCAN-API-KEY: test-data-key" --request GET https://api.hostedscan.com/v1/scans
```

## HTTP Responses

| Status Code | Details |
| :--- | :--- |
| 200 | OK - Successful request. |
| 400 | Bad Request - Invalid request parameters or missing required parameters. |
| 401 | Unauthorized - Invalid API key. |
| 404 | Not Found - No resource at the requested path. |
| 5xx | Internal Server Error - Something went wrong on our server. |



