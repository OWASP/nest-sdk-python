# Nest SDK

## Overview

OWASP Nest: Open Worldwide Application Security Project API

### Available Operations

* [settings_api_v1_api_root](#settings_api_v1_api_root) - Api Root

## settings_api_v1_api_root

Handle API root endpoint requests.

### Example Usage

<!-- UsageSnippet language="python" operationID="settings_api_v1_api_root" method="get" path="/api/v1/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    nest.settings_api_v1_api_root()

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |