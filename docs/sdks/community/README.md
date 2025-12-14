# Community

## Overview

### Available Operations

* [list_members](#list_members) - List members
* [get_member](#get_member) - Get member
* [list_organizations](#list_organizations) - List organizations
* [get_organization](#get_organization) - Get organization
* [list_snapshots](#list_snapshots) - List snapshots
* [get_snapshot](#get_snapshot) - Get snapshot
* [list_snapshot_chapters](#list_snapshot_chapters) - List new chapters in snapshot
* [list_snapshot_issues](#list_snapshot_issues) - List new issues in snapshot
* [list_snapshot_members](#list_snapshot_members) - List new members in snapshot
* [list_snapshot_projects](#list_snapshot_projects) - List new projects in snapshot
* [list_snapshot_releases](#list_snapshot_releases) - List new releases in snapshot

## list_members

Retrieve a paginated list of OWASP community members.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_members" method="get" path="/api/v0/members/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_members(location="India", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `company`                                                                           | *OptionalNullable[str]*                                                             | :heavy_minus_sign:                                                                  | Company of the user                                                                 |
| `location`                                                                          | *OptionalNullable[str]*                                                             | :heavy_minus_sign:                                                                  | Location of the member                                                              |
| `ordering`                                                                          | [OptionalNullable[models.ListMembersOrdering]](../../models/listmembersordering.md) | :heavy_minus_sign:                                                                  | Ordering field                                                                      |
| `page`                                                                              | *Optional[int]*                                                                     | :heavy_minus_sign:                                                                  | Page number                                                                         |
| `page_size`                                                                         | *Optional[int]*                                                                     | :heavy_minus_sign:                                                                  | Number of items per page                                                            |
| `retries`                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                    | :heavy_minus_sign:                                                                  | Configuration to override the default retry behavior of the client.                 |

### Response

**[models.PagedMember](../../models/pagedmember.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_member

Retrieve member details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_member" method="get" path="/api/v0/members/{member_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.get_member(member_id="OWASP")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `member_id`                                                         | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.MemberDetail](../../models/memberdetail.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.MemberError  | 404                 | application/json    |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## list_organizations

Retrieve a paginated list of GitHub organizations.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_organizations" method="get" path="/api/v0/organizations/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_organizations(location="United States of America", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                       | Type                                                                                            | Required                                                                                        | Description                                                                                     | Example                                                                                         |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `location`                                                                                      | *OptionalNullable[str]*                                                                         | :heavy_minus_sign:                                                                              | Location of the organization                                                                    | United States of America                                                                        |
| `ordering`                                                                                      | [OptionalNullable[models.ListOrganizationsOrdering]](../../models/listorganizationsordering.md) | :heavy_minus_sign:                                                                              | Ordering field                                                                                  |                                                                                                 |
| `page`                                                                                          | *Optional[int]*                                                                                 | :heavy_minus_sign:                                                                              | Page number                                                                                     |                                                                                                 |
| `page_size`                                                                                     | *Optional[int]*                                                                                 | :heavy_minus_sign:                                                                              | Number of items per page                                                                        |                                                                                                 |
| `retries`                                                                                       | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                | :heavy_minus_sign:                                                                              | Configuration to override the default retry behavior of the client.                             |                                                                                                 |

### Response

**[models.PagedOrganization](../../models/pagedorganization.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_organization

Retrieve project details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_organization" method="get" path="/api/v0/organizations/{organization_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.get_organization(organization_id="OWASP")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `organization_id`                                                   | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | OWASP                                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.OrganizationDetail](../../models/organizationdetail.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| models.OrganizationError | 404                      | application/json         |
| models.NestAPIError      | 4XX, 5XX                 | \*/\*                    |

## list_snapshots

Retrieve a paginated list of OWASP snapshots.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_snapshots" method="get" path="/api/v0/snapshots/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_snapshots(page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `ordering`                                                                              | [OptionalNullable[models.ListSnapshotsOrdering]](../../models/listsnapshotsordering.md) | :heavy_minus_sign:                                                                      | Ordering field                                                                          |
| `page`                                                                                  | *Optional[int]*                                                                         | :heavy_minus_sign:                                                                      | Page number                                                                             |
| `page_size`                                                                             | *Optional[int]*                                                                         | :heavy_minus_sign:                                                                      | Number of items per page                                                                |
| `retries`                                                                               | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                        | :heavy_minus_sign:                                                                      | Configuration to override the default retry behavior of the client.                     |

### Response

**[models.PagedSnapshot](../../models/pagedsnapshot.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## get_snapshot

Retrieve snapshot details.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_snapshot" method="get" path="/api/v0/snapshots/{snapshot_id}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.get_snapshot(snapshot_id="2025-02")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `snapshot_id`                                                       | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 | 2025-02                                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.SnapshotDetail](../../models/snapshotdetail.md)**

### Errors

| Error Type           | Status Code          | Content Type         |
| -------------------- | -------------------- | -------------------- |
| models.SnapshotError | 404                  | application/json     |
| models.NestAPIError  | 4XX, 5XX             | \*/\*                |

## list_snapshot_chapters

Retrieve a paginated list of new chapters in a snapshot.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_snapshot_chapters" method="get" path="/api/v0/snapshots/{snapshot_id}/chapters/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_snapshot_chapters(snapshot_id="2025-02", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           | Example                                                                                               |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `snapshot_id`                                                                                         | *str*                                                                                                 | :heavy_check_mark:                                                                                    | N/A                                                                                                   | 2025-02                                                                                               |
| `ordering`                                                                                            | [OptionalNullable[models.ListSnapshotChaptersOrdering]](../../models/listsnapshotchaptersordering.md) | :heavy_minus_sign:                                                                                    | Ordering field                                                                                        |                                                                                                       |
| `page`                                                                                                | *Optional[int]*                                                                                       | :heavy_minus_sign:                                                                                    | Page number                                                                                           |                                                                                                       |
| `page_size`                                                                                           | *Optional[int]*                                                                                       | :heavy_minus_sign:                                                                                    | Number of items per page                                                                              |                                                                                                       |
| `retries`                                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                      | :heavy_minus_sign:                                                                                    | Configuration to override the default retry behavior of the client.                                   |                                                                                                       |

### Response

**[models.PagedChapter](../../models/pagedchapter.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## list_snapshot_issues

Retrieve a paginated list of new issues in a snapshot.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_snapshot_issues" method="get" path="/api/v0/snapshots/{snapshot_id}/issues/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_snapshot_issues(snapshot_id="2025-02", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       | Example                                                                                           |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `snapshot_id`                                                                                     | *str*                                                                                             | :heavy_check_mark:                                                                                | N/A                                                                                               | 2025-02                                                                                           |
| `ordering`                                                                                        | [OptionalNullable[models.ListSnapshotIssuesOrdering]](../../models/listsnapshotissuesordering.md) | :heavy_minus_sign:                                                                                | Ordering field                                                                                    |                                                                                                   |
| `page`                                                                                            | *Optional[int]*                                                                                   | :heavy_minus_sign:                                                                                | Page number                                                                                       |                                                                                                   |
| `page_size`                                                                                       | *Optional[int]*                                                                                   | :heavy_minus_sign:                                                                                | Number of items per page                                                                          |                                                                                                   |
| `retries`                                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                  | :heavy_minus_sign:                                                                                | Configuration to override the default retry behavior of the client.                               |                                                                                                   |

### Response

**[models.PagedSnapshotIssue](../../models/pagedsnapshotissue.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## list_snapshot_members

Retrieve a paginated list of new members in a snapshot.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_snapshot_members" method="get" path="/api/v0/snapshots/{snapshot_id}/members/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_snapshot_members(snapshot_id="2025-02", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         | Example                                                                                             |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `snapshot_id`                                                                                       | *str*                                                                                               | :heavy_check_mark:                                                                                  | N/A                                                                                                 | 2025-02                                                                                             |
| `ordering`                                                                                          | [OptionalNullable[models.ListSnapshotMembersOrdering]](../../models/listsnapshotmembersordering.md) | :heavy_minus_sign:                                                                                  | Ordering field                                                                                      |                                                                                                     |
| `page`                                                                                              | *Optional[int]*                                                                                     | :heavy_minus_sign:                                                                                  | Page number                                                                                         |                                                                                                     |
| `page_size`                                                                                         | *Optional[int]*                                                                                     | :heavy_minus_sign:                                                                                  | Number of items per page                                                                            |                                                                                                     |
| `retries`                                                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                    | :heavy_minus_sign:                                                                                  | Configuration to override the default retry behavior of the client.                                 |                                                                                                     |

### Response

**[models.PagedMember](../../models/pagedmember.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## list_snapshot_projects

Retrieve a paginated list of new projects in a snapshot.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_snapshot_projects" method="get" path="/api/v0/snapshots/{snapshot_id}/projects/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_snapshot_projects(snapshot_id="2025-02", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           | Example                                                                                               |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `snapshot_id`                                                                                         | *str*                                                                                                 | :heavy_check_mark:                                                                                    | N/A                                                                                                   | 2025-02                                                                                               |
| `ordering`                                                                                            | [OptionalNullable[models.ListSnapshotProjectsOrdering]](../../models/listsnapshotprojectsordering.md) | :heavy_minus_sign:                                                                                    | Ordering field                                                                                        |                                                                                                       |
| `page`                                                                                                | *Optional[int]*                                                                                       | :heavy_minus_sign:                                                                                    | Page number                                                                                           |                                                                                                       |
| `page_size`                                                                                           | *Optional[int]*                                                                                       | :heavy_minus_sign:                                                                                    | Number of items per page                                                                              |                                                                                                       |
| `retries`                                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                      | :heavy_minus_sign:                                                                                    | Configuration to override the default retry behavior of the client.                                   |                                                                                                       |

### Response

**[models.PagedProject](../../models/pagedproject.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |

## list_snapshot_releases

Retrieve a paginated list of new releases in a snapshot.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_snapshot_releases" method="get" path="/api/v0/snapshots/{snapshot_id}/releases/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.community.list_snapshot_releases(snapshot_id="2025-02", page=1, page_size=100)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           | Example                                                                                               |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `snapshot_id`                                                                                         | *str*                                                                                                 | :heavy_check_mark:                                                                                    | N/A                                                                                                   | 2025-02                                                                                               |
| `ordering`                                                                                            | [OptionalNullable[models.ListSnapshotReleasesOrdering]](../../models/listsnapshotreleasesordering.md) | :heavy_minus_sign:                                                                                    | Ordering field                                                                                        |                                                                                                       |
| `page`                                                                                                | *Optional[int]*                                                                                       | :heavy_minus_sign:                                                                                    | Page number                                                                                           |                                                                                                       |
| `page_size`                                                                                           | *Optional[int]*                                                                                       | :heavy_minus_sign:                                                                                    | Number of items per page                                                                              |                                                                                                       |
| `retries`                                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                      | :heavy_minus_sign:                                                                                    | Configuration to override the default retry behavior of the client.                                   |                                                                                                       |

### Response

**[models.PagedSnapshotRelease](../../models/pagedsnapshotrelease.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| models.NestAPIError | 4XX, 5XX            | \*/\*               |