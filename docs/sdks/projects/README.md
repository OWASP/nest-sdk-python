# Projects
(*projects*)

## Overview

### Available Operations

* [list_projects](#list_projects) - List projects

## list_projects

Retrieve a paginated list of OWASP projects.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_projects" method="get" path="/api/v0/projects/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.projects.list_projects(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `level`                                                                               | [OptionalNullable[models.ProjectLevel]](../../models/projectlevel.md)                 | :heavy_minus_sign:                                                                    | Level of the project                                                                  |
| `ordering`                                                                            | [OptionalNullable[models.ListProjectsOrdering]](../../models/listprojectsordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `page_size`                                                                           | *OptionalNullable[int]*                                                               | :heavy_minus_sign:                                                                    | N/A                                                                                   |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.PagedProjectSchema](../../models/pagedprojectschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |