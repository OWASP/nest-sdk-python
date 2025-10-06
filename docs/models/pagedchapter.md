# PagedChapter


## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `current_page`                               | *int*                                        | :heavy_check_mark:                           | Current page number                          |
| `has_next`                                   | *bool*                                       | :heavy_check_mark:                           | Whether there is a next page                 |
| `has_previous`                               | *bool*                                       | :heavy_check_mark:                           | Whether there is a previous page             |
| `items`                                      | List[[models.Chapter](../models/chapter.md)] | :heavy_check_mark:                           | N/A                                          |
| `total_count`                                | *int*                                        | :heavy_check_mark:                           | Total number of items                        |
| `total_pages`                                | *int*                                        | :heavy_check_mark:                           | Total number of pages                        |