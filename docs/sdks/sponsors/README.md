# Sponsors
(*sponsors*)

## Overview

### Available Operations

* [list_sponsors](#list_sponsors) - List sponsors
* [get_sponsor](#get_sponsor) - Get sponsor

## list_sponsors

Retrieve a paginated list of OWASP sponsors.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_sponsors" method="get" path="/api/v0/sponsors/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.sponsors.list_sponsors(sponsor_type="Silver", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `is_member`                                                                           | *OptionalNullable[bool]*                                                              | :heavy_minus_sign:                                                                    | Member status of the sponsor                                                          |                                                                                       |
| `member_type`                                                                         | [OptionalNullable[models.MemberType]](../../models/membertype.md)                     | :heavy_minus_sign:                                                                    | Member type of the sponsor                                                            |                                                                                       |
| `sponsor_type`                                                                        | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Filter by the type of sponsorship (e.g., Gold, Silver, Platinum).                     | Silver                                                                                |
| `ordering`                                                                            | [OptionalNullable[models.ListSponsorsOrdering]](../../models/listsponsorsordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |                                                                                       |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | Page number                                                                           |                                                                                       |
| `page_size`                                                                           | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | Number of items per page                                                              |                                                                                       |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |                                                                                       |

### Response

**[models.PagedSponsor](../../models/pagedsponsor.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_sponsor

Retrieve a sponsor details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_sponsor" method="get" path="/api/v0/sponsors/{sponsor_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.sponsors.get_sponsor(sponsor_id="adobe")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `sponsor_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | adobe                                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.SponsorDetail](../../models/sponsordetail.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.SponsorError | 404                 | application/json    |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |