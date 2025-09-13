# Projects
(*projects*)

## Overview

### Available Operations

* [list_projects](#list_projects) - List projects
* [get_project](#get_project) - Get project

## list_projects

Retrieve a paginated list of OWASP projects.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_projects" method="get" path="/api/v0/projects/" -->
```python
import owasp_nest
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.projects.list_projects(ordering=owasp_nest.ListProjectsOrdering.MINUS_CREATED_AT, page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `level`                                                                               | [OptionalNullable[models.ProjectLevel]](../../models/projectlevel.md)                 | :heavy_minus_sign:                                                                    | Level of the project                                                                  |                                                                                       |
| `ordering`                                                                            | [OptionalNullable[models.ListProjectsOrdering]](../../models/listprojectsordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        | -created_at                                                                           |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `page_size`                                                                           | *OptionalNullable[int]*                                                               | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |                                                                                       |

### Response

**[models.PagedProjectSchema](../../models/pagedprojectschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_project

Retrieve project details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_project" method="get" path="/api/v0/projects/{project_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.projects.get_project(project_id="Nest")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | Nest                                                                |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.ProjectSchema](../../models/projectschema.md)**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| models.ProjectErrorResponse | 404                         | application/json            |
| models.NestAPIError         | 4XX, 5XX                    | \*/\*                       |