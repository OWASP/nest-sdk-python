# Chapters
(*chapters*)

## Overview

### Available Operations

* [apps_api_rest_v0_chapter_list_chapters](#apps_api_rest_v0_chapter_list_chapters) - List chapters
* [apps_api_rest_v0_chapter_get_chapter](#apps_api_rest_v0_chapter_get_chapter) - Get chapter

## apps_api_rest_v0_chapter_list_chapters

Retrieve a paginated list of OWASP chapters.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_chapter_list_chapters" method="get" path="/api/v0/chapters/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.apps_api_rest_v0_chapter_list_chapters(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `country`                                                                                                                     | *OptionalNullable[str]*                                                                                                       | :heavy_minus_sign:                                                                                                            | Country of the chapter                                                                                                        |
| `region`                                                                                                                      | *OptionalNullable[str]*                                                                                                       | :heavy_minus_sign:                                                                                                            | Region of the chapter                                                                                                         |
| `ordering`                                                                                                                    | [OptionalNullable[models.AppsAPIRestV0ChapterListChaptersOrdering]](../../models/appsapirestv0chapterlistchaptersordering.md) | :heavy_minus_sign:                                                                                                            | Ordering field                                                                                                                |
| `page`                                                                                                                        | *Optional[int]*                                                                                                               | :heavy_minus_sign:                                                                                                            | N/A                                                                                                                           |
| `page_size`                                                                                                                   | *OptionalNullable[int]*                                                                                                       | :heavy_minus_sign:                                                                                                            | N/A                                                                                                                           |
| `retries`                                                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                              | :heavy_minus_sign:                                                                                                            | Configuration to override the default retry behavior of the client.                                                           |

### Response

**[models.PagedChapterSchema](../../models/pagedchapterschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## apps_api_rest_v0_chapter_get_chapter

Retrieve chapter details.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_chapter_get_chapter" method="get" path="/api/v0/chapters/{chapter_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.apps_api_rest_v0_chapter_get_chapter(chapter_id="London")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `chapter_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | London                                                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.ChapterSchema](../../models/chapterschema.md)**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| models.ChapterErrorResponse | 404                         | application/json            |
| models.NestAPIError         | 4XX, 5XX                    | \*/\*                       |