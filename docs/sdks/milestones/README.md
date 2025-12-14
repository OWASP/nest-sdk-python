# Milestones

## Overview

### Available Operations

* [list_milestones](#list_milestones) - List milestones
* [get_milestone](#get_milestone) - Get milestone

## list_milestones

Retrieve a paginated list of GitHub milestones.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_milestones" method="get" path="/api/v0/milestones/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.milestones.list_milestones(organization="OWASP", repository="Nest", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               | Example                                                                                   |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `organization`                                                                            | *OptionalNullable[str]*                                                                   | :heavy_minus_sign:                                                                        | Organization that milestones belong to (filtered by repository owner)                     | OWASP                                                                                     |
| `repository`                                                                              | *OptionalNullable[str]*                                                                   | :heavy_minus_sign:                                                                        | Repository that milestones belong to                                                      | Nest                                                                                      |
| `state`                                                                                   | [OptionalNullable[models.State]](../../models/state.md)                                   | :heavy_minus_sign:                                                                        | Milestone state                                                                           |                                                                                           |
| `ordering`                                                                                | [OptionalNullable[models.ListMilestonesOrdering]](../../models/listmilestonesordering.md) | :heavy_minus_sign:                                                                        | N/A                                                                                       |                                                                                           |
| `page`                                                                                    | *Optional[int]*                                                                           | :heavy_minus_sign:                                                                        | Page number                                                                               |                                                                                           |
| `page_size`                                                                               | *Optional[int]*                                                                           | :heavy_minus_sign:                                                                        | Number of items per page                                                                  |                                                                                           |
| `retries`                                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                          | :heavy_minus_sign:                                                                        | Configuration to override the default retry behavior of the client.                       |                                                                                           |

### Response

**[models.PagedMilestone](../../models/pagedmilestone.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_milestone

Retrieve a specific GitHub milestone by organization, repository, and milestone number.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_milestone" method="get" path="/api/v0/milestones/{organization_id}/{repository_id}/{milestone_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.milestones.get_milestone(organization_id="OWASP", repository_id="Nest", milestone_id=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `organization_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `repository_id`                                                     | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | Nest                                                                |
| `milestone_id`                                                      | *int*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | 1                                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.MilestoneDetail](../../models/milestonedetail.md)**

### Errors

| Error Type            | Status Code           | Content Type          |
| --------------------- | --------------------- | --------------------- |
| models.MilestoneError | 404                   | application/json      |
| models.NestAPIError   | 4XX, 5XX              | \*/\*                 |