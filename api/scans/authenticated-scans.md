# Authenticated Scans

This page explains how to run an authenticated scan with the API. For general info on HostedScan's authenticated scanning features see - [https://hostedscan.com/authenticated-web-app-vulnerability-scan](https://hostedscan.com/authenticated-web-app-vulnerability-scan)

## Steps to run an authenticated scan

1. Create a target using the [create target API](../targets/create-target.md)&#x20;
2. Upload the recorded Selenium script to the target (see details below)
3. Start a scan with the [create scan API](create-scan.md) while sending `use_authentication: true` in the request.

## Uploading the recorded Selenium script

Make a POST request with `content-type: multipart/form-data` and one file to the endpoint `https:/api.hostedscan.com/v1/targets/:target_id/auth/selenium`.

#### Example using curl

```bash
curl -H "X-HOSTEDSCAN-API-KEY: <<your api key>>" -F file=@YouSeleniumRecording.side https://api.hostedscan.com/v1/targets/your-target-id/auth/selenium
```



