# Releases
(*releases*)

## Overview

### Available Operations

* [list_releases](#list_releases) - List releases
* [get_release](#get_release) - Get release

## list_releases

Retrieve a paginated list of GitHub releases.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_releases" method="get" path="/api/v0/releases/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.releases.list_releases(organization="OWASP", repository="Nest", tag_name="0.2.10", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `organization`                                                                        | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Organization that releases belong to (filtered by repository owner)                   | OWASP                                                                                 |
| `repository`                                                                          | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Repository that releases belong to                                                    | Nest                                                                                  |
| `tag_name`                                                                            | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Tag name of the release                                                               | 0.2.10                                                                                |
| `ordering`                                                                            | [OptionalNullable[models.ListReleasesOrdering]](../../models/listreleasesordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |                                                                                       |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | Page number                                                                           |                                                                                       |
| `page_size`                                                                           | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | Number of items per page                                                              |                                                                                       |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |                                                                                       |

### Response

**[models.PagedRelease](../../models/pagedrelease.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_release

Retrieve a specific GitHub release by organization, repository, and tag name.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_release" method="get" path="/api/v0/releases/{organization_id}/{repository_id}/{release_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.releases.get_release(organization_id="OWASP", repository_id="Nest", release_id="0.2.10")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `organization_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `repository_id`                                                     | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | Nest                                                                |
| `release_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | 0.2.10                                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.ReleaseDetail](../../models/releasedetail.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.ReleaseError | 404                 | application/json    |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |