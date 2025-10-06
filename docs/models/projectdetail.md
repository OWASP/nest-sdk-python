# ProjectDetail

Detail schema for Project (used in single item endpoints).


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `key`                                                                | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `level`                                                              | [models.ProjectLevel](../models/projectlevel.md)                     | :heavy_check_mark:                                                   | Enum for OWASP project levels.                                       |
| `name`                                                               | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `updated_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `description`                                                        | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |