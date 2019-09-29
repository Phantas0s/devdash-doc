---
title: Time
weight: 40
pre:  "<b>4. </b>"
---

The `start_date` and `end_date` options accept dates with format `2016-01-02` (year-month-day).

You can use as well aliases relative to the present day. The same alias can be a different date, depending if it's used as value for the `start_date` or the `end_date` option.

You can replace every `x` in the names by the numerical values you want.

| Name           | start_date                                           | end_date                                             |
| -------------- | ---------------------------------------------------- | ---------------------------------------------------  |
| today          | current day                                          | current day                                          |
| yesterday      | yesterday                                            | yesterday                                            |
| x_days_ago     | `x`th day before the current day                     | `x`th day before the current day                     |
|                |                                                      |                                                      |
| this_week      | first day of the actual week                         | last day of the actual week                          |
| last_week      | first day of the last week                           | last day of the last week                            |
| x_weeks_ago    | first day of the `x`th week before the current week  | last day of the `x`th week before the current week   |
|                |                                                      |                                                      |
| this_month     | first day of the actual month                        | last day of the actual month                         |
| last_month     | first day of the last month                          | last day of the last month                           |
| x_months_ago   | first day the `x`th month before the current month   | last day of the `x`th month before the current month |
|                |                                                      |                                                      |
| this_year      | first day of the actual year                         | last day of the actual year                          |
| last_year      | first day of the last year                           | last day of the last year                            |
| x_years_ago    | first day the `x`th year before the current year     | last day of the `x`th year before the current year   |

