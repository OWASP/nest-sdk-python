# SnapshotIssue

Schema for Snapshot Issue (used in list endpoints).


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `state`                                                              | [models.State](../models/state.md)                                   | :heavy_check_mark:                                                   | N/A                                                                  |
| `title`                                                              | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `updated_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `url`                                                                | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `organization_login`                                                 | *Nullable[str]*                                                      | :heavy_check_mark:                                                   | N/A                                                                  |
| `repository_name`                                                    | *Nullable[str]*                                                      | :heavy_check_mark:                                                   | N/A                                                                  |