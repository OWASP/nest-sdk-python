# Repositories

## Overview

### Available Operations

* [list_repositories](#list_repositories) - List repositories
* [get_repository](#get_repository) - Get repository

## list_repositories

Retrieve a paginated list of GitHub repositories.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_repositories" method="get" path="/api/v0/repositories/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.repositories.list_repositories(organization_id="OWASP", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `organization_id`                                                                             | *OptionalNullable[str]*                                                                       | :heavy_minus_sign:                                                                            | Organization that repositories belong to                                                      | OWASP                                                                                         |
| `ordering`                                                                                    | [OptionalNullable[models.ListRepositoriesOrdering]](../../models/listrepositoriesordering.md) | :heavy_minus_sign:                                                                            | Ordering field                                                                                |                                                                                               |
| `page`                                                                                        | *Optional[int]*                                                                               | :heavy_minus_sign:                                                                            | Page number                                                                                   |                                                                                               |
| `page_size`                                                                                   | *Optional[int]*                                                                               | :heavy_minus_sign:                                                                            | Number of items per page                                                                      |                                                                                               |
| `retries`                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                              | :heavy_minus_sign:                                                                            | Configuration to override the default retry behavior of the client.                           |                                                                                               |

### Response

**[models.PagedRepository](../../models/pagedrepository.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_repository

Retrieve a specific GitHub repository by organization and repository name.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_repository" method="get" path="/api/v0/repositories/{organization_id}/{repository_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.repositories.get_repository(organization_id="OWASP", repository_id="Nest")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `organization_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `repository_id`                                                     | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | Nest                                                                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.RepositoryDetail](../../models/repositorydetail.md)**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| models.RepositoryError | 404                    | application/json       |
| models.NestAPIError    | 4XX, 5XX               | \*/\*                  |