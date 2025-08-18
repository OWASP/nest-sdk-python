<!-- Start SDK Example Usage [usage] -->
```python
# Synchronous Example
from owasp_nest import Nest


with Nest(
    api_key_auth="<YOUR_API_KEY_HERE>",
) as nest:

    nest.settings_api_v1_api_root()

    # Use the SDK ...
```

</br>

The same SDK client can also be used to make asynchronous requests by importing asyncio.
```python
# Asynchronous Example
import asyncio
from owasp_nest import Nest

async def main():

    async with Nest(
        api_key_auth="<YOUR_API_KEY_HERE>",
    ) as nest:

        await nest.settings_api_v1_api_root_async()

        # Use the SDK ...

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->