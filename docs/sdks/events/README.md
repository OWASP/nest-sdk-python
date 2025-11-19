# Events
(*events*)

## Overview

### Available Operations

* [list_events](#list_events) - List events
* [get_event](#get_event) - Get event

## list_events

Retrieve a paginated list of OWASP events.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_events" method="get" path="/api/v0/events/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.events.list_events(page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `latitude_gte`                                                                    | *OptionalNullable[float]*                                                         | :heavy_minus_sign:                                                                | Latitude greater than or equal to                                                 |
| `latitude_lte`                                                                    | *OptionalNullable[float]*                                                         | :heavy_minus_sign:                                                                | Latitude less than or equal to                                                    |
| `longitude_gte`                                                                   | *OptionalNullable[float]*                                                         | :heavy_minus_sign:                                                                | Longitude greater than or equal to                                                |
| `longitude_lte`                                                                   | *OptionalNullable[float]*                                                         | :heavy_minus_sign:                                                                | Longitude less than or equal to                                                   |
| `ordering`                                                                        | [OptionalNullable[models.ListEventsOrdering]](../../models/listeventsordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |
| `is_upcoming`                                                                     | *OptionalNullable[bool]*                                                          | :heavy_minus_sign:                                                                | Filter for upcoming events                                                        |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | Page number                                                                       |
| `page_size`                                                                       | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | Number of items per page                                                          |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.PagedEvent](../../models/pagedevent.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_event

Retrieve an event details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_event" method="get" path="/api/v0/events/{event_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.events.get_event(event_id="owasp-global-appsec-usa-2025-washington-dc")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `event_id`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | owasp-global-appsec-usa-2025-washington-dc                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.EventDetail](../../models/eventdetail.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.EventError   | 404                 | application/json    |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |