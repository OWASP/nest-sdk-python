# Chapters
(*chapters*)

## Overview

### Available Operations

* [list_chapters](#list_chapters) - List chapters
* [get_chapter](#get_chapter) - Get chapter

## list_chapters

Retrieve a paginated list of OWASP chapters.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_chapters" method="get" path="/api/v1/chapters/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", region="Asia", page=1)

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

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_chapter

Retrieve chapter details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_chapter" method="get" path="/api/v1/chapters/{key}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.get_chapter(key="<key>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `key`                                                               | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ChapterSchema](../../models/chapterschema.md)**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| models.ChapterErrorResponse | 404                         | application/json            |
| models.NestAPIError         | 4XX, 5XX                    | \*/\*                       |