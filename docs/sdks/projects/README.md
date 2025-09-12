# Projects
(*projects*)

## Overview

### Available Operations

* [apps_api_rest_v0_project_list_projects](#apps_api_rest_v0_project_list_projects) - List projects
* [apps_api_rest_v0_project_get_project](#apps_api_rest_v0_project_get_project) - Get project

## apps_api_rest_v0_project_list_projects

Retrieve a paginated list of OWASP projects.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_project_list_projects" method="get" path="/api/v0/projects/" -->
```python
import owasp_nest
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.projects.apps_api_rest_v0_project_list_projects(ordering=owasp_nest.AppsAPIRestV0ProjectListProjectsOrdering.MINUS_CREATED_AT, page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   | Example                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `level`                                                                                                                       | [OptionalNullable[models.ProjectLevel]](../../models/projectlevel.md)                                                         | :heavy_minus_sign:                                                                                                            | Level of the project                                                                                                          |                                                                                                                               |
| `ordering`                                                                                                                    | [OptionalNullable[models.AppsAPIRestV0ProjectListProjectsOrdering]](../../models/appsapirestv0projectlistprojectsordering.md) | :heavy_minus_sign:                                                                                                            | Ordering field                                                                                                                | -created_at                                                                                                                   |
| `page`                                                                                                                        | *Optional[int]*                                                                                                               | :heavy_minus_sign:                                                                                                            | N/A                                                                                                                           |                                                                                                                               |
| `page_size`                                                                                                                   | *OptionalNullable[int]*                                                                                                       | :heavy_minus_sign:                                                                                                            | N/A                                                                                                                           |                                                                                                                               |
| `retries`                                                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                              | :heavy_minus_sign:                                                                                                            | Configuration to override the default retry behavior of the client.                                                           |                                                                                                                               |

### Response

**[models.PagedProjectSchema](../../models/pagedprojectschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## apps_api_rest_v0_project_get_project

Retrieve project details.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_project_get_project" method="get" path="/api/v0/projects/{project_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.projects.apps_api_rest_v0_project_get_project(project_id="Nest")

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