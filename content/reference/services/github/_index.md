---
title: Github
weight: 3 
---

## Authorization

1. Go to your Github account in your favorite browser
2. Click on your avatar (top right corner)
3. Click on "Settings"
4. Click on "Developer settings"
5. Click on "Personal access tokens"
6. You don't need to select any scope for DevDash, except if you want to read data from your private repositories.
7. Generate a **new token you will add in your DevDash configuration**.


## Widgets available

| Name                      | Description                                                                       | Comment                                                                                     |
| ------------------------  | --------------------------------------------------------------------------------  | -----------------------------------------------------------------------------               |
| github.box_stars          | Number of stars of a precise repository                                           |                                                                                             |
| github.box_watchers       | Number of watchers of a precise repository                                        |                                                                                             |
| github.box_open_issues    | Number of open issues of a precise repository                                     |                                                                                             |
| github.table_branches     | All branches of a precise repository                                              |                                                                                             |
| github.table_issues       | All issues (and their states) of a precise repository                             |                                                                                             |
| github.table_repositories | Table of all repositories with count different information (see `metrics` option) |                                                                                             |
| github.bar_views          | Github traffic of the repository's page the last 14 days                          | Doesn't accept start_date / end_date option                                                 |
| github.bar_commits        | Give the number of commit per week (maximum last 52 weeks)                        | stard_date / end_date option must be "x_weeks_go". x must be a number at least 0 at most 52 |
| github.bar_stars          | Display stars given to a repository overtime                                      |                                                                                             |

## Widget Options

### Table Widgets

| Name            | Description                    | Default value                        | Examples                                          | Availability                                                     |
| --------------- | ------------------------------ | ------------------------------------ | ------------------------------------------------- | --------------------------------------------------               |
| row_limit       | Limit the number of rows       | 5                                    | 5, 100                                            |                                                                  |
| order           | Order of the list              | `updated`                            | `created`, `updated`, `pushed`, `full_name`       | Not available for `github.table_branches`, `github.table_issues` |
| metrics         | Column display                 | `stars,watchers,forks,open_issues`   | `stars,forks`                                     | Not available for `github.table_branches`, `github.table_issues` |

### Bar Widgets

| Name            | Description                                                                   | Default value     | Examples                                 | Availability                                             |
| --------------- | ----------------------------------------------------------------------------- | ----------------- | ---------------------------------------- | -------------------------------------------------------- |
| start_date      | Start date of time period                                                     | `7_days_ago`      | `2018-01-01`, `2_weeks_ago`              | Not available for `github.bar_views`                     |
| end_date        | End date of time period                                                       | `today`           | `2018-01-31`, `2_weeks_ago`              | Not available for `github.bar_views`                     |
| scope           | Owner commits or everybody commits                                            | `owner`           | `owner`, `all`                           | Only available for `github.bar_commits`                  |
