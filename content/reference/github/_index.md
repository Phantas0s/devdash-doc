---
title: Github
weight: 20
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

| Name                      | Description                                                                       | Comment                                                                       |
| ------------------------  | --------------------------------------------------------------------------------  | ----------------------------------------------------------------------------- |
| github.box_stars          | Number of stars of a precise repository                                           |                                                                               |
| github.box_watchers       | Number of watchers of a precise repository                                        |                                                                               |
| github.box_open_issues    | Number of open issues of a precise repository                                     |                                                                               |
| github.table_branches     | All branches of a precise repository                                              |                                                                               |
| github.table_issues       | All issues (and their states) of a precise repository                             |                                                                               |
| github.table_repositories | Table of all repositories with count different information (see `metrics` option) |                                                                               |
| github.bar_views   | Github traffic of the repository's page the last 14 days                          | Doesn't accept start_date / end_date option                                   |
| github.bar_commits        | Give the number of commit per week (maximum last 52 weeks)                        | stard_date / end_date option must be "x_weeks_go" or "today". x must be < 52  |

## Widget Options

### Table Widgets

#### Data Options

| Name            | Description                    | Default value                        | Examples                                          | Not available for                                  |
| --------------- | ------------------------------ | ------------------------------------ | ------------------------------------------------- | -------------------------------------------------- |
| row_limit       | Limit the number of rows       | 5                                    | 5, 100                                            |                                                    |
| order           | Order of the list              | `updated`                            | `created`, `updated`, `pushed`, `full_name`       | `github.table_branches`, `github.table_issues`     |
| metrics         | Column display                 | `stars,watchers,forks,open_issues`   | `stars,forks`                                     | `github.table_branches`, `github.table_issues`     |

#### Display Options

| Name               | Description      | Default value                   | Examples                                      |
| ------------------ | ---------------- | ------------------------------- | --------------------------------------------- |
| title              | Title            | `Depending on the widget`       | `Users `                                      |
| title_color        | Title color      | `Default color`                 | `yellow`, `red` (see [colors](#colors))       |
| border_color       | Border color     | `Default color`                 | `yellow`, `red` (see [colors](#colors))       |
| text_color         | Text color       | `Default color`                 | `yellow`, `red` (see [colors](#colors))       |

### Bar Widgets

#### Data Options

| Name            | Description                                                                   | Default value     | Examples                                 | Not available for                                        |
| --------------- | ----------------------------------------------------------------------------- | ----------------- | ---------------------------------------- | -------------------------------------------------------- |
| start_date      | Start date of time period                                                     | `7_days_ago`      | `2018-01-01`, `2_weeks_ago`              | github.bar_views                                  |
| end_date        | End date of time period                                                       | `today`           | `2018-01-31`, `2_weeks_ago`              | github.bar_views                                  |

#### Display Options

| Name              | Description                                                   | Default value                 | Examples                                    |
| ----------------- | ------------------------------------------------------------- | ----------------------------- | ------------------------------------------- |
| title             | Title                                                         | `Depending on the widget`     | `Users `                                    |
| border_color      | Border color                                                  | `Default color`               | `yellow`, `red` (see [colors](#colors))     |
| height            | Height                                                        | `10`                          | `5`                                         |
| title_color       | Title color                                                   | `Default color`               | `yellow`, `red` (see [colors](#colors))     |
| text_color        | Text color                                                    | `Default color`               | `yellow`, `red` (see [colors](#colors))     |
| num_color         | Color of numerical data                                       | `Default color`               | `yellow`, `red` (see [colors](#colors))     |
| empty_num_color   | Color of numerical data when the bar is too small to appear   | `Default color`               | `yellow`, `red` (see [colors](#colors))     |
| bar_color         | Bar color                                                     | `Default color`               | `yellow`, `red` (see [colors](#colors))     |
| bar_gap           | Gap size between the bars                                     | `0`                           | `5`, `10`                                   |
| bar_width         | Bar width                                                     | `6`                           | `5`, `10`                                   |

