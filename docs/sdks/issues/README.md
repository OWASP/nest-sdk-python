# Issues
(*issues*)

## Overview

### Available Operations

* [list_issues](#list_issues) - List issues

## list_issues

Retrieve a paginated list of GitHub issues.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_issues" method="get" path="/api/v1/issues/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.issues.list_issues(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `state`                                                                           | [OptionalNullable[models.State]](../../models/state.md)                           | :heavy_minus_sign:                                                                | State of the issue                                                                |
| `ordering`                                                                        | [OptionalNullable[models.ListIssuesOrdering]](../../models/listissuesordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | N/A                                                                               |
| `page_size`                                                                       | *OptionalNullable[int]*                                                           | :heavy_minus_sign:                                                                | N/A                                                                               |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.PagedIssueSchema](../../models/pagedissueschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |