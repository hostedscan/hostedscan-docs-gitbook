# Overview

HostedScan offers a comprehensive REST API. API access is available to Enterprise plan customers.

## Authentication

Authenticate by setting the X-HOSTEDSCAN-API-KEY request header as your API key.

## HTTP Responses

| Status Code | Details |
| :--- | :--- |
| 200 | OK - Successful request. |
| 400 | Bad Request - Invalid request parameters or missing required parameters. |
| 401 | Unauthorized - Invalid API key. |
| 404 | Not Found - No resource at the requested path. |
| 5xx | Internal Server Error - Something went wrong on our server. |



