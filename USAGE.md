<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
from owasp_nest import Nest


with Nest(
    api_key="<YOUR_API_KEY_HERE>",
) as nest:

    res = nest.chapters.list_chapters(country="India", region="Asia", page=1)

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

        res = await nest.chapters.list_chapters_async(country="India", region="Asia", page=1)

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->