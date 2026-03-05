# Issue

Schema for Issue (minimal fields for list display).


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `state`                                                              | [models.IssueState](../models/issuestate.md)                         | :heavy_check_mark:                                                   | Issue state choices.                                                 |
| `title`                                                              | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |
| `updated_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | N/A                                                                  |
| `url`                                                                | *str*                                                                | :heavy_check_mark:                                                   | N/A                                                                  |