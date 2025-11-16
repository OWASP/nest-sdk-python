# RepositoryDetail

Detail schema for Repository (used in single item endpoints).


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `name`                                                               | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `updated_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `commits_count`                                                      | *int*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `contributors_count`                                                 | *int*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `description`                                                        | *OptionalNullable[str]*                                              | :heavy_minus_sign:                                                   | N/A                                                                  |
| `forks_count`                                                        | *int*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `open_issues_count`                                                  | *int*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `stars_count`                                                        | *int*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |