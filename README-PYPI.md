# owasp-nest

Developer-friendly & type-safe Python SDK specifically catered to leverage *owasp-nest* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=owasp-nest&utm_campaign=python"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20Speakeasy-212015?style=for-the-badge&logoColor=FBE331&logo=speakeasy&labelColor=545454" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>

<!-- Start Summary [summary] -->
## Summary

OWASP Nest: Open Worldwide Application Security Project API
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [owasp-nest](https://github.com/OWASP/nest-sdk-python/blob/master/#owasp-nest)
  * [SDK Installation](https://github.com/OWASP/nest-sdk-python/blob/master/#sdk-installation)
  * [IDE Support](https://github.com/OWASP/nest-sdk-python/blob/master/#ide-support)
  * [SDK Example Usage](https://github.com/OWASP/nest-sdk-python/blob/master/#sdk-example-usage)
  * [Authentication](https://github.com/OWASP/nest-sdk-python/blob/master/#authentication)
  * [Available Resources and Operations](https://github.com/OWASP/nest-sdk-python/blob/master/#available-resources-and-operations)
  * [Retries](https://github.com/OWASP/nest-sdk-python/blob/master/#retries)
  * [Error Handling](https://github.com/OWASP/nest-sdk-python/blob/master/#error-handling)
  * [Server Selection](https://github.com/OWASP/nest-sdk-python/blob/master/#server-selection)
  * [Custom HTTP Client](https://github.com/OWASP/nest-sdk-python/blob/master/#custom-http-client)
  * [Resource Management](https://github.com/OWASP/nest-sdk-python/blob/master/#resource-management)
  * [Debugging](https://github.com/OWASP/nest-sdk-python/blob/master/#debugging)
* [Development](https://github.com/OWASP/nest-sdk-python/blob/master/#development)
  * [Maturity](https://github.com/OWASP/nest-sdk-python/blob/master/#maturity)
  * [Contributions](https://github.com/OWASP/nest-sdk-python/blob/master/#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!NOTE]
> **Python version upgrade policy**
>
> Once a Python version reaches its [official end of life date](https://devguide.python.org/versions/), a 3-month grace period is provided for users to upgrade. Following this grace period, the minimum python version supported in the SDK will be updated.

The SDK can be installed with *uv*, *pip*, or *poetry* package managers.

### uv

*uv* is a fast Python package installer and resolver, designed as a drop-in replacement for pip and pip-tools. It's recommended for its speed and modern Python tooling capabilities.

```bash
uv add owasp-nest
```

### PIP

*PIP* is the default package installer for Python, enabling easy installation and management of packages from PyPI via the command line.

```bash
pip install owasp-nest
```

### Poetry

*Poetry* is a modern tool that simplifies dependency management and package publishing by using a single `pyproject.toml` file to handle project metadata and dependencies.

```bash
poetry add owasp-nest
```

### Shell and script usage with `uv`

You can use this SDK in a Python shell with [uv](https://docs.astral.sh/uv/) and the `uvx` command that comes with it like so:

```shell
uvx --from owasp-nest python
```

It's also possible to write a standalone Python script without needing to set up a whole project like so:

```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.9"
# dependencies = [
#     "owasp-nest",
# ]
# ///

from owasp_nest import Nest

sdk = Nest(
  # SDK arguments
)

# Rest of script here...
```

Once that is saved to a file, you can run it with `uv run script.py` where
`script.py` can be replaced with the actual file name.
<!-- End SDK Installation [installation] -->

<!-- Start IDE Support [idesupport] -->
## IDE Support

### PyCharm

Generally, the SDK will work well with most IDEs out of the box. However, when using PyCharm, you can enjoy much better integration with Pydantic by installing an additional plugin.

- [PyCharm Pydantic Plugin](https://docs.pydantic.dev/latest/integrations/pycharm/)
<!-- End IDE Support [idesupport] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```python
# Synchronous Example
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", page=1, page_size=100)

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asynchronous requests by importing asyncio.

```python
# Asynchronous Example
import asyncio
from owasp_nest import Nest

async def main():

    async with Nest(
        api_key="<YOUR_API_KEY_HERE>",
    ) as nest:

        res = await nest.chapters.list_chapters_async(country="India", page=1, page_size=100)

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name      | Type   | Scheme  |
| --------- | ------ | ------- |
| `api_key` | apiKey | API key |

To authenticate with the API the `api_key` parameter must be set when initializing the SDK client instance. For example:
```python
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", page=1, page_size=100)

    # Handle response
    print(res)

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [chapters](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/chapters/README.md)

* [list_chapters](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/chapters/README.md#list_chapters) - List chapters
* [get_chapter](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/chapters/README.md#get_chapter) - Get chapter

### [committees](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/committees/README.md)

* [list_committees](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/committees/README.md#list_committees) - List committees
* [get_committee](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/committees/README.md#get_committee) - Get committee

### [community](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md)

* [list_members](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_members) - List members
* [get_member](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#get_member) - Get member
* [list_organizations](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_organizations) - List organizations
* [get_organization](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#get_organization) - Get organization
* [list_snapshots](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_snapshots) - List snapshots
* [get_snapshot](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#get_snapshot) - Get snapshot
* [list_snapshot_chapters](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_snapshot_chapters) - List new chapters in snapshot
* [list_snapshot_issues](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_snapshot_issues) - List new issues in snapshot
* [list_snapshot_members](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_snapshot_members) - List new members in snapshot
* [list_snapshot_projects](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_snapshot_projects) - List new projects in snapshot
* [list_snapshot_releases](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/community/README.md#list_snapshot_releases) - List new releases in snapshot

### [events](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/events/README.md)

* [list_events](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/events/README.md#list_events) - List events
* [get_event](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/events/README.md#get_event) - Get event

### [issues](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/issues/README.md)

* [list_issues](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/issues/README.md#list_issues) - List issues
* [get_issue](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/issues/README.md#get_issue) - Get issue

### [milestones](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/milestones/README.md)

* [list_milestones](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/milestones/README.md#list_milestones) - List milestones
* [get_milestone](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/milestones/README.md#get_milestone) - Get milestone

### [projects](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/projects/README.md)

* [list_projects](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/projects/README.md#list_projects) - List projects
* [get_project](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/projects/README.md#get_project) - Get project

### [releases](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/releases/README.md)

* [list_releases](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/releases/README.md#list_releases) - List releases
* [get_release](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/releases/README.md#get_release) - Get release

### [repositories](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/repositories/README.md)

* [list_repositories](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/repositories/README.md#list_repositories) - List repositories
* [get_repository](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/repositories/README.md#get_repository) - Get repository

### [sponsors](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/sponsors/README.md)

* [list_sponsors](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/sponsors/README.md#list_sponsors) - List sponsors
* [get_sponsor](https://github.com/OWASP/nest-sdk-python/blob/master/docs/sdks/sponsors/README.md#get_sponsor) - Get sponsor

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `RetryConfig` object to the call:
```python
from owasp_nest import Nest
from owasp_nest.utils import BackoffStrategy, RetryConfig


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", page=1, page_size=100,
        RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False))

    # Handle response
    print(res)

```

If you'd like to override the default retry strategy for all operations that support retries, you can use the `retry_config` optional parameter when initializing the SDK:
```python
from owasp_nest import Nest
from owasp_nest.utils import BackoffStrategy, RetryConfig


with Nest(
    retry_config=RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False),
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", page=1, page_size=100)

    # Handle response
    print(res)

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`NestError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/nesterror.py) is the base class for all HTTP error responses. It has the following properties:

| Property           | Type             | Description                                                                             |
| ------------------ | ---------------- | --------------------------------------------------------------------------------------- |
| `err.message`      | `str`            | Error message                                                                           |
| `err.status_code`  | `int`            | HTTP response status code eg `404`                                                      |
| `err.headers`      | `httpx.Headers`  | HTTP response headers                                                                   |
| `err.body`         | `str`            | HTTP body. Can be empty string if no body is returned.                                  |
| `err.raw_response` | `httpx.Response` | Raw HTTP response                                                                       |
| `err.data`         |                  | Optional. Some errors may contain structured data. [See Error Classes](https://github.com/OWASP/nest-sdk-python/blob/master/#error-classes). |

### Example
```python
from owasp_nest import Nest, models


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:
    res = None
    try:

        res = nest.chapters.get_chapter(chapter_id="London")

        # Handle response
        print(res)


    except models.NestError as e:
        # The base class for HTTP error responses
        print(e.message)
        print(e.status_code)
        print(e.body)
        print(e.headers)
        print(e.raw_response)

        # Depending on the method different errors may be thrown
        if isinstance(e, models.ChapterError):
            print(e.data.message)  # str
```

### Error Classes
**Primary error:**
* [`NestError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/nesterror.py): The base class for HTTP error responses.

<details><summary>Less common errors (17)</summary>

<br />

**Network errors:**
* [`httpx.RequestError`](https://www.python-httpx.org/exceptions/#httpx.RequestError): Base class for request errors.
    * [`httpx.ConnectError`](https://www.python-httpx.org/exceptions/#httpx.ConnectError): HTTP client was unable to make a request to a server.
    * [`httpx.TimeoutException`](https://www.python-httpx.org/exceptions/#httpx.TimeoutException): HTTP request timed out.


**Inherit from [`NestError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/nesterror.py)**:
* [`ChapterError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/chaptererror.py): Chapter error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`CommitteeError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/committeeerror.py): Committee error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`EventError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/eventerror.py): Event error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`IssueError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/issueerror.py): Issue error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`MemberError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/membererror.py): Member error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`OrganizationError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/organizationerror.py): Organization error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`SnapshotError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/snapshoterror.py): Snapshot error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`MilestoneError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/milestoneerror.py): Milestone error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`ProjectError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/projecterror.py): Project error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`ReleaseError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/releaseerror.py): Release error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`RepositoryError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/repositoryerror.py): Repository error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`SponsorError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/sponsorerror.py): Sponsor error schema. Status code `404`. Applicable to 1 of 29 methods.*
* [`ResponseValidationError`](https://github.com/OWASP/nest-sdk-python/blob/master/./src/owasp_nest/models/responsevalidationerror.py): Type mismatch between the response data and the expected Pydantic model. Provides access to the Pydantic validation error via the `cause` attribute.

</details>

\* Check [the method documentation](https://github.com/OWASP/nest-sdk-python/blob/master/#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `server_url: str` optional parameter when initializing the SDK client instance. For example:
```python
from owasp_nest import Nest


with Nest(
    server_url="https://nest.owasp.dev",
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", page=1, page_size=100)

    # Handle response
    print(res)

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Python SDK makes API calls using the [httpx](https://www.python-httpx.org/) HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with your own HTTP client instance.
Depending on whether you are using the sync or async version of the SDK, you can pass an instance of `HttpClient` or `AsyncHttpClient` respectively, which are Protocol's ensuring that the client has the necessary methods to make API calls.
This allows you to wrap the client with your own custom logic, such as adding custom headers, logging, or error handling, or you can just pass an instance of `httpx.Client` or `httpx.AsyncClient` directly.

For example, you could specify a header for every request that this sdk makes as follows:
```python
from owasp_nest import Nest
import httpx

http_client = httpx.Client(headers={"x-custom-header": "someValue"})
s = Nest(client=http_client)
```

or you could wrap the client with your own custom logic:
```python
from owasp_nest import Nest
from owasp_nest.httpclient import AsyncHttpClient
import httpx

class CustomClient(AsyncHttpClient):
    client: AsyncHttpClient

    def __init__(self, client: AsyncHttpClient):
        self.client = client

    async def send(
        self,
        request: httpx.Request,
        *,
        stream: bool = False,
        auth: Union[
            httpx._types.AuthTypes, httpx._client.UseClientDefault, None
        ] = httpx.USE_CLIENT_DEFAULT,
        follow_redirects: Union[
            bool, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
    ) -> httpx.Response:
        request.headers["Client-Level-Header"] = "added by client"

        return await self.client.send(
            request, stream=stream, auth=auth, follow_redirects=follow_redirects
        )

    def build_request(
        self,
        method: str,
        url: httpx._types.URLTypes,
        *,
        content: Optional[httpx._types.RequestContent] = None,
        data: Optional[httpx._types.RequestData] = None,
        files: Optional[httpx._types.RequestFiles] = None,
        json: Optional[Any] = None,
        params: Optional[httpx._types.QueryParamTypes] = None,
        headers: Optional[httpx._types.HeaderTypes] = None,
        cookies: Optional[httpx._types.CookieTypes] = None,
        timeout: Union[
            httpx._types.TimeoutTypes, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
        extensions: Optional[httpx._types.RequestExtensions] = None,
    ) -> httpx.Request:
        return self.client.build_request(
            method,
            url,
            content=content,
            data=data,
            files=files,
            json=json,
            params=params,
            headers=headers,
            cookies=cookies,
            timeout=timeout,
            extensions=extensions,
        )

s = Nest(async_client=CustomClient(httpx.AsyncClient()))
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Resource Management [resource-management] -->
## Resource Management

The `Nest` class implements the context manager protocol and registers a finalizer function to close the underlying sync and async HTTPX clients it uses under the hood. This will close HTTP connections, release memory and free up other resources held by the SDK. In short-lived Python programs and notebooks that make a few SDK method calls, resource management may not be a concern. However, in longer-lived programs, it is beneficial to create a single SDK instance via a [context manager][context-manager] and reuse it across the application.

[context-manager]: https://docs.python.org/3/reference/datamodel.html#context-managers

```python
from owasp_nest import Nest
def main():

    with Nest(
        api_key="<YOUR_API_KEY_HERE>",
    ) as nest:
        # Rest of application here...


# Or when using async:
async def amain():

    async with Nest(
        api_key="<YOUR_API_KEY_HERE>",
    ) as nest:
        # Rest of application here...
```
<!-- End Resource Management [resource-management] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass your own logger class directly into your SDK.
```python
from owasp_nest import Nest
import logging

logging.basicConfig(level=logging.DEBUG)
s = Nest(debug_logger=logging.getLogger("owasp_nest"))
```
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation.
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release.

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=owasp-nest&utm_campaign=python)
