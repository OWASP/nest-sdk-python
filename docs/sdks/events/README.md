# Events
(*events*)

## Overview

### Available Operations

* [list_events](#list_events) - List events

## list_events

Retrieve a paginated list of OWASP events.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_events" method="get" path="/api/v1/events/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.events.list_events(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `ordering`                                                                        | [OptionalNullable[models.ListEventsOrdering]](../../models/listeventsordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | N/A                                                                               |
| `page_size`                                                                       | *OptionalNullable[int]*                                                           | :heavy_minus_sign:                                                                | N/A                                                                               |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.PagedEventSchema](../../models/pagedeventschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |