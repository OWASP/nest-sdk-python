# Chapters

## Overview

### Available Operations

* [list_chapters](#list_chapters) - List chapters
* [get_chapter](#get_chapter) - Get chapter

## list_chapters

Retrieve a paginated list of OWASP chapters.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_chapters" method="get" path="/api/v0/chapters/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `latitude_gte`                                                                        | *OptionalNullable[float]*                                                             | :heavy_minus_sign:                                                                    | Latitude greater than or equal to                                                     |
| `latitude_lte`                                                                        | *OptionalNullable[float]*                                                             | :heavy_minus_sign:                                                                    | Latitude less than or equal to                                                        |
| `longitude_gte`                                                                       | *OptionalNullable[float]*                                                             | :heavy_minus_sign:                                                                    | Longitude greater than or equal to                                                    |
| `longitude_lte`                                                                       | *OptionalNullable[float]*                                                             | :heavy_minus_sign:                                                                    | Longitude less than or equal to                                                       |
| `country`                                                                             | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Country of the chapter                                                                |
| `ordering`                                                                            | [OptionalNullable[models.ListChaptersOrdering]](../../models/listchaptersordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | Page number                                                                           |
| `page_size`                                                                           | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | Number of items per page                                                              |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |

### Response

**[models.PagedChapter](../../models/pagedchapter.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_chapter

Retrieve chapter details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_chapter" method="get" path="/api/v0/chapters/{chapter_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.get_chapter(chapter_id="London")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `chapter_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | London                                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.ChapterDetail](../../models/chapterdetail.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.ChapterError | 404                 | application/json    |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |