# Community
(*community*)

## Overview

### Available Operations

* [list_members](#list_members) - List members
* [apps_api_rest_v0_member_get_member](#apps_api_rest_v0_member_get_member) - Get member
* [apps_api_rest_v0_organization_list_organization](#apps_api_rest_v0_organization_list_organization) - List organizations
* [apps_api_rest_v0_organization_get_organization](#apps_api_rest_v0_organization_get_organization) - Get organization

## list_members

Retrieve a paginated list of OWASP community members.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_members" method="get" path="/api/v0/members/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_members(location="India", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `company`                                                                           | *OptionalNullable[str]*                                                             | :heavy_minus_sign:                                                                  | Company of the user                                                                 |
| `location`                                                                          | *OptionalNullable[str]*                                                             | :heavy_minus_sign:                                                                  | Location of the member                                                              |
| `ordering`                                                                          | [OptionalNullable[models.ListMembersOrdering]](../../models/listmembersordering.md) | :heavy_minus_sign:                                                                  | Ordering field                                                                      |
| `page`                                                                              | *Optional[int]*                                                                     | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `page_size`                                                                         | *OptionalNullable[int]*                                                             | :heavy_minus_sign:                                                                  | N/A                                                                                 |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |

### Response

**[models.PagedMemberSchema](../../models/pagedmemberschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## apps_api_rest_v0_member_get_member

Retrieve member details.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_member_get_member" method="get" path="/api/v0/members/{member_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.apps_api_rest_v0_member_get_member(member_id="OWASP")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `member_id`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.MemberSchema](../../models/memberschema.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models.MemberErrorResponse | 404                        | application/json           |
| models.NestAPIError        | 4XX, 5XX                   | \*/\*                      |

## apps_api_rest_v0_organization_list_organization

Retrieve a paginated list of GitHub organizations.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_organization_list_organization" method="get" path="/api/v0/organizations/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.apps_api_rest_v0_organization_list_organization(location="United States of America", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                                                       | Type                                                                                                                                            | Required                                                                                                                                        | Description                                                                                                                                     | Example                                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `location`                                                                                                                                      | *OptionalNullable[str]*                                                                                                                         | :heavy_minus_sign:                                                                                                                              | Location of the organization                                                                                                                    | United States of America                                                                                                                        |
| `ordering`                                                                                                                                      | [OptionalNullable[models.AppsAPIRestV0OrganizationListOrganizationOrdering]](../../models/appsapirestv0organizationlistorganizationordering.md) | :heavy_minus_sign:                                                                                                                              | Ordering field                                                                                                                                  |                                                                                                                                                 |
| `page`                                                                                                                                          | *Optional[int]*                                                                                                                                 | :heavy_minus_sign:                                                                                                                              | N/A                                                                                                                                             |                                                                                                                                                 |
| `page_size`                                                                                                                                     | *OptionalNullable[int]*                                                                                                                         | :heavy_minus_sign:                                                                                                                              | N/A                                                                                                                                             |                                                                                                                                                 |
| `retries`                                                                                                                                       | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                                                | :heavy_minus_sign:                                                                                                                              | Configuration to override the default retry behavior of the client.                                                                             |                                                                                                                                                 |

### Response

**[models.PagedOrganizationSchema](../../models/pagedorganizationschema.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## apps_api_rest_v0_organization_get_organization

Retrieve project details.

### Example Usage

<!-- UsageSnippet language="python" operationID="apps_api_rest_v0_organization_get_organization" method="get" path="/api/v0/organizations/{organization_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.apps_api_rest_v0_organization_get_organization(organization_id="OWASP")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `organization_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.OrganizationSchema](../../models/organizationschema.md)**

### Errors

| Error Type                       | Status Code                      | Content Type                     |
| -------------------------------- | -------------------------------- | -------------------------------- |
| models.OrganizationErrorResponse | 404                              | application/json                 |
| models.NestAPIError              | 4XX, 5XX                         | \*/\*                            |