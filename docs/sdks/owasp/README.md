# Owasp
(*owasp*)

## Overview

### Available Operations

* [list_chapters](#list_chapters) - List chapters
* [list_committees](#list_committees) - List committees
* [list_events](#list_events) - List events
* [list_projects](#list_projects) - List projects

## list_chapters

Retrieve a paginated list of OWASP chapters.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_chapters" method="get" path="/api/v1/owasp/chapters/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.owasp.list_chapters(country="India", region="Asia", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `country`                                                                             | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Country of the chapter                                                                | India                                                                                 |
| `region`                                                                              | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Region of the chapter                                                                 | Asia                                                                                  |
| `ordering`                                                                            | [OptionalNullable[models.ListChaptersOrdering]](../../models/listchaptersordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |                                                                                       |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `page_size`                                                                           | *OptionalNullable[int]*                                                               | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |                                                                                       |

### Response

**[models.PagedChapterSchema](../../models/pagedchapterschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_committees

Retrieve a paginated list of OWASP committees.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_committees" method="get" path="/api/v1/owasp/committees/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.owasp.list_committees(page=1)

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

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_events

Retrieve a paginated list of OWASP events.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_events" method="get" path="/api/v1/owasp/events/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.owasp.list_events(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `ordering`                                                                        | [OptionalNullable[models.ListEventsOrdering]](../../models/listeventsordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | N/A                                                                               |
| `page_size`                                                                       | *OptionalNullable[int]*                                                           | :heavy_minus_sign:                                                                | N/A                                                                               |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.PagedEventSchema](../../models/pagedeventschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_projects

Retrieve a paginated list of OWASP projects.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_projects" method="get" path="/api/v1/owasp/projects/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.owasp.list_projects(page=1)

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

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |