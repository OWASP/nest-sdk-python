# Issues
(*issues*)

## Overview

### Available Operations

* [list_issues](#list_issues) - List issues
* [get_issue](#get_issue) - Get issue

## list_issues

Retrieve a paginated list of GitHub issues.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_issues" method="get" path="/api/v0/issues/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.issues.list_issues(organization="OWASP", repository="Nest", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       | Example                                                                           |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `organization`                                                                    | *OptionalNullable[str]*                                                           | :heavy_minus_sign:                                                                | Organization that issues belong to (filtered by repository owner)                 | OWASP                                                                             |
| `repository`                                                                      | *OptionalNullable[str]*                                                           | :heavy_minus_sign:                                                                | Repository that issues belong to                                                  | Nest                                                                              |
| `state`                                                                           | [OptionalNullable[models.State]](../../models/state.md)                           | :heavy_minus_sign:                                                                | Issue state                                                                       |                                                                                   |
| `ordering`                                                                        | [OptionalNullable[models.ListIssuesOrdering]](../../models/listissuesordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |                                                                                   |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | Page number                                                                       |                                                                                   |
| `page_size`                                                                       | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | Number of items per page                                                          |                                                                                   |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |                                                                                   |

### Response

**[models.PagedIssue](../../models/pagedissue.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_issue

Retrieve a specific GitHub issue by organization, repository, and issue number.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_issue" method="get" path="/api/v0/issues/{organization_id}/{repository_id}/{issue_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.issues.get_issue(organization_id="OWASP", repository_id="Nest", issue_id=1234)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `organization_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `repository_id`                                                     | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | Nest                                                                |
| `issue_id`                                                          | *int*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | 1234                                                                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.IssueDetail](../../models/issuedetail.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.IssueError   | 404                 | application/json    |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |