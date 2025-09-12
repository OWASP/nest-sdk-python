# Committees
(*committees*)

## Overview

### Available Operations

* [list_committees](#list_committees) - List committees
* [apps_api_rest_v0_committee_get_chapter](#apps_api_rest_v0_committee_get_chapter) - Get committee

## list_committees

Retrieve a paginated list of OWASP committees.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_committees" method="get" path="/api/v0/committees/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.committees.list_committees(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `ordering`                                                                                | [OptionalNullable[models.ListCommitteesOrdering]](../../models/listcommitteesordering.md) | :heavy_minus_sign:                                                                        | Ordering field                                                                            |
| `page`                                                                                    | *Optional[int]*                                                                           | :heavy_minus_sign:                                                                        | N/A                                                                                       |
| `page_size`                                                                               | *OptionalNullable[int]*                                                                   | :heavy_minus_sign:                                                                        | N/A                                                                                       |
| `retries`                                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                          | :heavy_minus_sign:                                                                        | Configuration to override the default retry behavior of the client.                       |

### Response

**[models.PagedCommitteeSchema](../../models/pagedcommitteeschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## apps_api_rest_v0_committee_get_chapter

Retrieve committee details.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_committee_get_chapter" method="get" path="/api/v0/committees/{committee_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.committees.apps_api_rest_v0_committee_get_chapter(committee_id="project")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `committee_id`                                                      | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | project                                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.CommitteeSchema](../../models/committeeschema.md)**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| models.CommitteeErrorResponse | 404                           | application/json              |
| models.NestAPIError           | 4XX, 5XX                      | \*/\*                         |