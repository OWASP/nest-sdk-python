# Releases
(*releases*)

## Overview

### Available Operations

* [list_releases](#list_releases) - List releases

## list_releases

Retrieve a paginated list of GitHub releases.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_releases" method="get" path="/api/v0/releases/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.releases.list_releases(tag_name="v1.0.0", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `tag_name`                                                                            | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Tag name of the release                                                               | v1.0.0                                                                                |
| `ordering`                                                                            | [OptionalNullable[models.ListReleasesOrdering]](../../models/listreleasesordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |                                                                                       |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `page_size`                                                                           | *OptionalNullable[int]*                                                               | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |                                                                                       |

### Response

**[models.PagedReleaseSchema](../../models/pagedreleaseschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |