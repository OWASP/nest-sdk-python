# Events
(*events*)

## Overview

### Available Operations

* [apps_api_rest_v0_event_list_events](#apps_api_rest_v0_event_list_events) - List events

## apps_api_rest_v0_event_list_events

Retrieve a paginated list of OWASP events.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_event_list_events" method="get" path="/api/v0/events/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.events.apps_api_rest_v0_event_list_events(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                             | Type                                                                                                                  | Required                                                                                                              | Description                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `ordering`                                                                                                            | [OptionalNullable[models.AppsAPIRestV0EventListEventsOrdering]](../../models/appsapirestv0eventlisteventsordering.md) | :heavy_minus_sign:                                                                                                    | Ordering field                                                                                                        |
| `page`                                                                                                                | *Optional[int]*                                                                                                       | :heavy_minus_sign:                                                                                                    | N/A                                                                                                                   |
| `page_size`                                                                                                           | *OptionalNullable[int]*                                                                                               | :heavy_minus_sign:                                                                                                    | N/A                                                                                                                   |
| `retries`                                                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                      | :heavy_minus_sign:                                                                                                    | Configuration to override the default retry behavior of the client.                                                   |

### Response

**[models.PagedEventSchema](../../models/pagedeventschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |