# Repositories
(*repositories*)

## Overview

### Available Operations

* [list_repositories](#list_repositories) - List repositories

## list_repositories

Retrieve a paginated list of GitHub repositories.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_repositories" method="get" path="/api/v1/repositories/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.repositories.list_repositories(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `ordering`                                                                                    | [OptionalNullable[models.ListRepositoriesOrdering]](../../models/listrepositoriesordering.md) | :heavy_minus_sign:                                                                            | Ordering field                                                                                |
| `page`                                                                                        | *Optional[int]*                                                                               | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `page_size`                                                                                   | *OptionalNullable[int]*                                                                       | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `retries`                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                              | :heavy_minus_sign:                                                                            | Configuration to override the default retry behavior of the client.                           |

### Response

**[models.PagedRepositorySchema](../../models/pagedrepositoryschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |