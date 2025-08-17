# GitHub
(*git_hub*)

## Overview

### Available Operations

* [list_issues](#list_issues) - List issues
* [list_labels](#list_labels) - List labels
* [list_organizations](#list_organizations) - List organizations
* [list_releases](#list_releases) - List releases
* [list_repositories](#list_repositories) - List repositories
* [list_users](#list_users) - List users
* [get_user](#get_user) - Get user by login

## list_issues

Retrieve a paginated list of GitHub issues.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_issues" method="get" path="/api/v1/github/issues/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.list_issues(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `state`                                                                           | [OptionalNullable[models.State]](../../models/state.md)                           | :heavy_minus_sign:                                                                | State of the issue                                                                |
| `ordering`                                                                        | [OptionalNullable[models.ListIssuesOrdering]](../../models/listissuesordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | N/A                                                                               |
| `page_size`                                                                       | *OptionalNullable[int]*                                                           | :heavy_minus_sign:                                                                | N/A                                                                               |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |

### Response

**[models.PagedIssueSchema](../../models/pagedissueschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_labels

Retrieve a paginated list of GitHub labels.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_labels" method="get" path="/api/v1/github/labels/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.list_labels(color="d93f0b", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       | Example                                                                           |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `color`                                                                           | *OptionalNullable[str]*                                                           | :heavy_minus_sign:                                                                | Color of the label                                                                | d93f0b                                                                            |
| `ordering`                                                                        | [OptionalNullable[models.ListLabelsOrdering]](../../models/listlabelsordering.md) | :heavy_minus_sign:                                                                | Ordering field                                                                    |                                                                                   |
| `page`                                                                            | *Optional[int]*                                                                   | :heavy_minus_sign:                                                                | N/A                                                                               |                                                                                   |
| `page_size`                                                                       | *OptionalNullable[int]*                                                           | :heavy_minus_sign:                                                                | N/A                                                                               |                                                                                   |
| `retries`                                                                         | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                  | :heavy_minus_sign:                                                                | Configuration to override the default retry behavior of the client.               |                                                                                   |

### Response

**[models.PagedLabelSchema](../../models/pagedlabelschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_organizations

Retrieve a paginated list of GitHub organizations.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_organizations" method="get" path="/api/v1/github/organizations/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.list_organizations(location="United States of America", page=1)

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

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_releases

Retrieve a paginated list of GitHub releases.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_releases" method="get" path="/api/v1/github/releases/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.list_releases(tag_name="v1.0.0", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `tag_name`                                                                            | *OptionalNullable[str]*                                                               | :heavy_minus_sign:                                                                    | Tag name of the release                                                               | v1.0.0                                                                                |
| `ordering`                                                                            | [OptionalNullable[models.ListReleasesOrdering]](../../models/listreleasesordering.md) | :heavy_minus_sign:                                                                    | Ordering field                                                                        |                                                                                       |
| `page`                                                                                | *Optional[int]*                                                                       | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `page_size`                                                                           | *OptionalNullable[int]*                                                               | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |
| `retries`                                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                      | :heavy_minus_sign:                                                                    | Configuration to override the default retry behavior of the client.                   |                                                                                       |

### Response

**[models.PagedReleaseSchema](../../models/pagedreleaseschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_repositories

Retrieve a paginated list of GitHub repositories.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_repositories" method="get" path="/api/v1/github/repositories/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.list_repositories(page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `ordering`                                                                                    | [OptionalNullable[models.ListRepositoriesOrdering]](../../models/listrepositoriesordering.md) | :heavy_minus_sign:                                                                            | Ordering field                                                                                |
| `page`                                                                                        | *Optional[int]*                                                                               | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `page_size`                                                                                   | *OptionalNullable[int]*                                                                       | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `retries`                                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                              | :heavy_minus_sign:                                                                            | Configuration to override the default retry behavior of the client.                           |

### Response

**[models.PagedRepositorySchema](../../models/pagedrepositoryschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## list_users

Retrieve a paginated list of GitHub users.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_users" method="get" path="/api/v1/github/users/" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.list_users(location="India", page=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     | Example                                                                         |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `company`                                                                       | *OptionalNullable[str]*                                                         | :heavy_minus_sign:                                                              | Company of the user                                                             |                                                                                 |
| `location`                                                                      | *OptionalNullable[str]*                                                         | :heavy_minus_sign:                                                              | Location of the user                                                            | India                                                                           |
| `ordering`                                                                      | [OptionalNullable[models.ListUsersOrdering]](../../models/listusersordering.md) | :heavy_minus_sign:                                                              | Ordering field                                                                  |                                                                                 |
| `page`                                                                          | *Optional[int]*                                                                 | :heavy_minus_sign:                                                              | N/A                                                                             |                                                                                 |
| `page_size`                                                                     | *OptionalNullable[int]*                                                         | :heavy_minus_sign:                                                              | N/A                                                                             |                                                                                 |
| `retries`                                                                       | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                | :heavy_minus_sign:                                                              | Configuration to override the default retry behavior of the client.             |                                                                                 |

### Response

**[models.PagedUserSchema](../../models/pageduserschema.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| models.NestError | 4XX, 5XX         | \*/\*            |

## get_user

Retrieve a GitHub user by login.

### Example Usage

<!-- UsageSnippet language="python" operationID="get_user" method="get" path="/api/v1/github/users/{login}" -->
```python
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.git_hub.get_user(login="Enos13")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `login`                                                             | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.UserSchema](../../models/userschema.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| models.UserErrorResponse | 404                      | application/json         |
| models.NestError         | 4XX, 5XX                 | \*/\*                    |