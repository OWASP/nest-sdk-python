# Committees
(*committees*)

## Overview

### Available Operations

* [list_committees](#list_committees) - List committees

## list_committees

Retrieve a paginated list of OWASP committees.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_committees" method="get" path="/api/v1/committees/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.committees.list_committees(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `ordering`                                                                                | [OptionalNullable[models.ListCommitteesOrdering]](../../models/listcommitteesordering.md) | :heavy_minus_sign:                                                                        | Ordering field                                                                            |
| `page`                                                                                    | *Optional[int]*                                                                           | :heavy_minus_sign:                                                                        | N/A                                                                                       |
| `page_size`                                                                               | *OptionalNullable[int]*                                                                   | :heavy_minus_sign:                                                                        | N/A                                                                                       |
| `retries`                                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                          | :heavy_minus_sign:                                                                        | Configuration to override the default retry behavior of the client.                       |

### Response

**[models.PagedCommitteeSchema](../../models/pagedcommitteeschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |