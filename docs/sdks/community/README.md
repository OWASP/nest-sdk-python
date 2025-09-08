# Community
(*community*)

## Overview

### Available Operations

* [list_members](#list_members) - List members
* [get_member](#get_member) - Get member by login
* [list_organizations](#list_organizations) - List organizations

## list_members

Retrieve a paginated list of OWASP community members.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_members" method="get" path="/api/v1/members/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_members(location="India", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         | Example                                                                             |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `company`                                                                           | *OptionalNullable[str]*                                                             | :heavy_minus_sign:                                                                  | Company of the user                                                                 |                                                                                     |
| `location`                                                                          | *OptionalNullable[str]*                                                             | :heavy_minus_sign:                                                                  | Location of the member                                                              | India                                                                               |
| `ordering`                                                                          | [OptionalNullable[models.ListMembersOrdering]](../../models/listmembersordering.md) | :heavy_minus_sign:                                                                  | Ordering field                                                                      |                                                                                     |
| `page`                                                                              | *Optional[int]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |                                                                                     |
| `page_size`                                                                         | *OptionalNullable[int]*                                                             | :heavy_minus_sign:                                                                  | N/A                                                                                 |                                                                                     |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |                                                                                     |

### Response

**[models.PagedMemberSchema](../../models/pagedmemberschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_member

Retrieve a member by login.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_member" method="get" path="/api/v1/members/{login}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.get_member(login="Stanton97")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `login`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.MemberSchema](../../models/memberschema.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.MemberErrorResponse | 404                        | application/json           |
| models.NestAPIError        | 4XX, 5XX                   | \*/\*                      |

## list_organizations

Retrieve a paginated list of GitHub organizations.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_organizations" method="get" path="/api/v1/organizations/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_organizations(location="United States of America", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                       | Type                                                                                            | Required                                                                                        | Description                                                                                     | Example                                                                                         |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `location`                                                                                      | *OptionalNullable[str]*                                                                         | :heavy_minus_sign:                                                                              | Location of the organization                                                                    | United States of America                                                                        |
| `ordering`                                                                                      | [OptionalNullable[models.ListOrganizationsOrdering]](../../models/listorganizationsordering.md) | :heavy_minus_sign:                                                                              | Ordering field                                                                                  |                                                                                                 |
| `page`                                                                                          | *Optional[int]*                                                                                 | :heavy_minus_sign:                                                                              | N/A                                                                                             |                                                                                                 |
| `page_size`                                                                                     | *OptionalNullable[int]*                                                                         | :heavy_minus_sign:                                                                              | N/A                                                                                             |                                                                                                 |
| `retries`                                                                                       | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                | :heavy_minus_sign:                                                                              | Configuration to override the default retry behavior of the client.                             |                                                                                                 |

### Response

**[models.PagedOrganizationSchema](../../models/pagedorganizationschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |