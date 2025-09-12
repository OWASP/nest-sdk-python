<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
from owasp_nest import Nest


with Nest(
    api_key_header="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.apps_api_rest_v0_chapter_list_chapters(page=1)

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
        api_key_header="<YOUR_API_KEY_HERE>",
    ) as nest:

        res = await nest.chapters.apps_api_rest_v0_chapter_list_chapters_async(page=1)

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->