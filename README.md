![travis CLI](https://travis-ci.org/Phantas0s/devdash.svg?branch=master&style=for-the-badge) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/ec1e19b08f3b40d19f3acaf93e3e186b)](https://www.codacy.com/app/Phantas0s/devdash?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Phantas0s/devdash&amp;utm_campaign=Badge_Grade)  [![Go Report Card](https://goreportcard.com/badge/github.com/Phantas0s/devdash)](https://goreportcard.com/report/github.com/Phantas0s/devdash) [![Hits-of-Code](https://hitsofcode.com/github/phantas0s/devdash)](https://hitsofcode.com/view/github/phantas0s/devdash) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 
![logo of devdash with a gopher](./doc/img/logo.jpg) 
[![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=DevDash%20-%20Highly%20Configurable%20Terminal%20Dashboard%20For%20Developers:&url=https%3A%2F%2Fgithub.com%2Fphantas0s%2Fdevdash&hashtags=developers,dashboard,terminal,CLI,golang) [![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/T6T4W5K0)

DevDash is a highly configurable terminal dashboard for developers, who want to choose the most up-to-date metrics they need, at one place.

# Why using DevDash?

* *Choose* the metrics you specifically need.
* All the important data in your cosy terminal.
* Pull data from Github, Google Analytics or Google Search Console. More services to come!
* Unlimited amount of different dashboards with different configurations.
* Widgets' data refreshed automatically.
* A huge amount of flexibility compared to other terminal dashboards:
  * Choose the widgets you want.
  * Place your widgets where you want.
  * Choose the data you want to display, the colors you want to use, and a lot of other things for each widget.

# Menu

* [Installation](#installation)
* [Getting Started](#getting-started)
* [Authorization and permissions](#authorization-and-permissions)
* [Configuration examples](#configuration-examples)
* [Structure of the config file](#structure-of-the-config-file)
* [Widget types](#widget-types)
* [Configuration reference](#configuration-reference)
* [General references](#general-references)
* [Acknowledgement](#acknowledgement)
* [Contribute](#contribute)
* [Licence](#licence)

# Configuration examples

You can click on each screenshot to see the config of these dashboards.

## Google Analytics

[<img src="./example/img/ga-1.png" alt="monitor_widget" type="image/png" >](./example/ga-1.yml)
[<img src="./example/img/ga-2.png" alt="monitor_widget" type="image/png" >](./example/ga-2.yml)

## Google Search Console

[<img src="./example/img/gsc-1.png" alt="monitor_widget" type="image/png" >](./example/gsc-1.yml)

## Github 

[<img src="./example/img/git-1.png" alt="monitor_widget" type="image/png" >](./example/git-1.yml)

## Real life dashboard

[<img src="./example/img/mix-1.png" alt="monitor_widget" type="image/png" >](./example/mix-1.yml)

# Structure of the config file

Since a diagram is better than a wall of text, here we go:

![structure of the configuration file](./doc/img/struct.png)

# Widget types

There are three category of widgets:

* `box` - a single value in a box
* `bar` - a bar diagram with multiple values overtime (dates on the x-axis)
* `table` - data in a table

# Configuration reference

## General

The general configuration of your dashboard.

| Name     | Description                                           | Default value | Examples |
|----------|-------------------------------------------------------|---------------|----------|
| refresh  | The cycle's duration of refreshing data, in seconds   | 600           | 600      |

## Monitoring

### Service configuration

```yml
    services:
      monitor:
        address: "https://www.my-website.net"
```

### Widgets available

| Name                     | Description                                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| mon.box_availability     | Send an HTTP request to the address specified in he service configuration and display the response's status code   |

##### Data Options

None.

##### Display Options

| Name           | Description    | Default value             | Examples                                  |
| -------------- | -------------- | ------------------------- | ----------------------------------------- |
| title          | Title          | Depending on the widget   | ` Users `                                 |
| height         | Height         | `10`                      | `5`                                       |
| title_color    | Title color    | `Default color`           | `yellow`, `red` (see [colors](/display/colors/))   |
| border_color   | Border color   | `Default color`           | `yellow`, `red` (see [colors](/display/colors/))   |
| text_color     | Text color     | `Default color`           | `yellow`, `red` (see [colors](/display/colors/))   |

## Github

### Service configuration

```yml
    services:
      github:
        token: myToken
        owner: myName
        repository: myCoolRepo
```

The repository is not mandatory. However, you will need to precise the repository for each widget fetching data for a specific one.

### Widgets available

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

### Widget Options

#### Table Widgets

##### Data Options

| Name            | Description                    | Default value                        | Examples                                          | Not available for                                  |
| --------------- | ------------------------------ | ------------------------------------ | ------------------------------------------------- | -------------------------------------------------- |
| row_limit       | Limit the number of rows       | 5                                    | 5, 100                                            |                                                    |
| order           | Order of the list              | `updated`                            | `created`, `updated`, `pushed`, `full_name`       | `github.table_branches`, `github.table_issues`     |
| metrics         | Column display                 | `stars,watchers,forks,open_issues`   | `stars,forks`                                     | `github.table_branches`, `github.table_issues`     |

##### Display Options

| Name               | Description      | Default value                   | Examples                                      |
| ------------------ | ---------------- | ------------------------------- | --------------------------------------------- |
| title              | Title            | `Depending on the widget`       | `Users `                                      |
| title_color        | Title color      | `Default color`                 | `yellow`, `red` (see [colors](/display/colors/))       |
| border_color       | Border color     | `Default color`                 | `yellow`, `red` (see [colors](/display/colors/))       |
| text_color         | Text color       | `Default color`                 | `yellow`, `red` (see [colors](/display/colors/))       |

#### Bar Widgets

##### Data Options

| Name            | Description                                                                   | Default value     | Examples                                 | Not available for                                        |
| --------------- | ----------------------------------------------------------------------------- | ----------------- | ---------------------------------------- | -------------------------------------------------------- |
| start_date      | Start date of time period                                                     | `7_days_ago`      | `2018-01-01`, `2_weeks_ago`              | github.bar_views                                  |
| end_date        | End date of time period                                                       | `today`           | `2018-01-31`, `2_weeks_ago`              | github.bar_views                                  |

##### Display Options

| Name              | Description                                                   | Default value                 | Examples                                    |
| ----------------- | ------------------------------------------------------------- | ----------------------------- | ------------------------------------------- |
| title             | Title                                                         | `Depending on the widget`     | `Users `                                    |
| border_color      | Border color                                                  | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| height            | Height                                                        | `10`                          | `5`                                         |
| title_color       | Title color                                                   | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| text_color        | Text color                                                    | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| num_color         | Color of numerical data                                       | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| empty_num_color   | Color of numerical data when the bar is too small to appear   | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| bar_color         | Bar color                                                     | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| bar_gap           | Gap size between the bars                                     | `0`                           | `5`, `10`                                   |
| bar_width         | Bar width                                                     | `6`                           | `5`, `10`                                   |

## Google Analytics

### Service configuration

```yml
    services:
      google_analytics:
        keyfile: goanalytics-abc123.json
        view_id: 456789123
```

### Widgets available

| Name                           | Description                                                              |
| ------------------------------ | ------------------------------------------------------------------------ |
| ga.box_real_time               | Number of users currently on the website                                 |
| ga.box_total                   | Total of any metric on a given time period                               |
| ga.bar_sessions                | Count of sessions                                                        |
| ga.bar_bounces                 | Count of bounce sessions                                                 |
| ga.bar_users                   | Count of users                                                           |
| ga.bar_returning               | Count of returning users                                                 |
| ga.bar_pages                   | Count of sessions (or any other metric like users) on specific page(s)   |
| ga.bar                         | Count of theoretically any metrics from Google Analytics                 |
| ga.bar_new_returning           | Count of new and returning users                                         |
| ga.table_pages                 | Display chosen data about pages                                          |
| ga.table_traffic_sources       | Display Data about traffic sources                                       |
| ga.table                       | Display theoretically any metrics from Google Analytics                  |

### Widget Options

#### Bar Widgets

##### Data Options

| Name            | Description                                                                   | Default value     | Examples                                 | Not available for                                        |
| --------------- | ----------------------------------------------------------------------------- | ----------------- | ---------------------------------------- | -------------------------------------------------------- |
| start_date      | Start date of time period                                                     | `7_days_ago`      | `2018-01-01`, `2_weeks_ago`              |                                                          |
| end_date        | End date of time period                                                       | `today`           | `2018-01-31`, `2_weeks_ago`              |                                                          |
| time_period     | Time period represented by a bar                                              | `days`            | `days`, `months`, `years`                |                                                          |
| metric          | Google analytics metric                                                       | `sessions`        | `page_views`, `bounces`, `entrances`     | `ga.bar_pages`, `ga.bar_returning`                       |
| dimensions      | Google analytics dimensions. Multiple value possible separated with a comma   |                   | `page_path`, `user_types`                | `ga.bar_pages`, `ga.bar_bounces`, `ga.bar_returning`     |
| filters         | Query filter (prefix `-` to exclude)                                          |                   | `value`, `-value`                        |                                                          |

##### Display Options

| Name              | Description                                                   | Default value                 | Examples                                    |
| ----------------- | ------------------------------------------------------------- | ----------------------------- | ------------------------------------------- |
| title             | Title                                                         | `Depending on the widget`     | `Users `                                    |
| border_color      | Border color                                                  | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| height            | Height                                                        | `10`                          | `5`                                         |
| title_color       | Title color                                                   | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| text_color        | Text color                                                    | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| num_color         | Color of numerical data                                       | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| empty_num_color   | Color of numerical data when the bar is too small to appear   | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| bar_color         | Bar color                                                     | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| bar_gap           | Gap size between the bars                                     | `0`                           | `5`, `10`                                   |
| bar_width         | Bar width                                                     | `6`                           | `5`, `10`                                   |

#### Table widgets

##### Data Options

| Name              | Description                                                                 | Default value                                       | Examples                                       | Not used by                  |
| ----------------- | --------------------------------------------------------------------------- | --------------------------------------------------- | ---------------------------------------------- | ---------------------------- |
| start_date        | Start date of time period                                                   | `7_days_ago`                                        | `2018-01-01`, `2_weeks_ago`                    |                              |
| end_date          | End date of time period                                                     | `today`                                             | `2018-01-31`, `2_weeks_ago`                    |                              |
| metrics           | Google analytics metrics. Multiple values possible separated with a comma   | `sessions,page_views,entrances,unique_page_views`   | `bounces,sessions`, `entrances`                |                              |
| dimension         | Google analytics dimension                                                  | `page_path`                                         | `2018-01-31`, `2_weeks_ago`                    | `ga.table_traffic_sources`   |
| orders            | Order of the result. Multiple value possible separated with a comma         | `sessions desc`                                     | `sessions desc,page_views asc`. `page_views`   |                              |
| filters           | Query filter (prefix `-` to exclude)                                        |                                                     | `value`, `-value`                              |                              |
| row_limit         | Limit the number of rows                                                    | 5                                                   | 5, 100                                         |                              |
| character_limit   | Limit the number of characters of the dimension column                      | 20                                                  | 100, 200                                       |                              |

##### Display Options

| Name             | Description    | Default value                 | Examples                                    |
| ---------------- | -------------- | ----------------------------- | ------------------------------------------- |
| title            | Title          | `Depending on the widget`     | `Users `                                    |
| title_color      | Title color    | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| border_color     | Border color   | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |
| text_color       | Text color     | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))     |

#### Box widgets

##### Data Options

| Name             | Description                       | Default value   | Examples                               |
| ---------------- | --------------------------------- | --------------- | -------------------------------------- |
| start_date       | Start date of time period         | `7_days_ago`    | `2018-01-01`, `2_weeks_ago`            |
| end_date         | End date of time period           | `today`         | `2018-01-31`, `2_weeks_ago`            |
| metric           | Google analytics' metric          | `sessions`      | `page_views`, `bounces`, `entrances`   |

##### Display Options

| Name               | Description        | Default value                       | Examples                                  |
| ------------------ | ------------------ | ----------------------------------- | ----------------------------------------- |
| title              | Title              | `Depending on the widget`           | `Users `                                  |
| height             | Height             | `10`                                | `5`                                       |
| title_color        | Title color        | `Default color`                     | `yellow`, `red` (see [colors](/display/colors/))   |
| border_color       | Border color       | `Default color`                     | `yellow`, `red` (see [colors](/display/colors/))   |
| text_color         | Text color         | `Default color`                     | `yellow`, `red` (see [colors](/display/colors/))   |

## Google Search Console

### Service configuration

```yml
    services:
      google_search_console:
        keyfile: goanalytics-abc123.json
```

### Widgets available

| Name                | Description                                                                             |
| ------------------- | --------------------------------------------------------------------------------------- |
| gsc.table_pages     | Display clicks, impressions, ctr, position for pages                                    |
| gsc.table_queries   | Display clicks, impressions, ctr, position for queries                                  |
| gsc.table            | Display theoretically any dimension from Google Search Console on a given time period   |

### Widget Options

#### Table widgets

##### Data Options

| Name              | Description                                                                       | Default value                       | Examples                                       | Not used by         |
| ----------------- | --------------------------------------------------------------------------------- | ----------------------------------- | ---------------------------------------------- | ------------------- |
| start_date        | Start date of time period                                                         | `7_days_ago`                        | `2018-01-01`, `2_weeks_ago`                    |                     |
| end_date          | End date of time period                                                           | `today`                             | `2018-01-31`, `2_weeks_ago`                    |                     |
| metrics           | Google Search Console metrics (multiple values possible separated with comma)     | `clicks,impressions,ctr,position`   | `query`, `page`                                | `gsc.table_pages`   |
| dimension         | Google Search Console dimension (multiple values possible separated with comma)   | `quert`,                            | `2018-01-31`, `2_weeks_ago`                    |                     |
| orders            | Order of the result (multiple values possible separated with comma)               | `sessions desc`                     | `sessions desc,page_views asc`. `page_views`   |                     |
| filters           | Filter the default dimension (prefix `-` to exclude)                              |                                     | `value`, `-super value`                        |                     |
| row_limit         | Limit the number of rows                                                          | 5                                   | 5, 100                                         |                     |
| character_limit   | Limit the number of characters for the first column (dimension)                   | 1000                                | 100, 200                                       |                     |

##### Display Options

| Name             | Description      | Default value                 | Examples                                  |
| ---------------- | ---------------- | ----------------------------- | ----------------------------------------- |
| title            | Title            | `Depending on the widget`     | `Users `                                  |
| border_color     | Border color     | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))   |
| text_color       | text_color       | `Default color`               | `yellow`, `red` (see [colors](/display/colors/))   |

# General references

## Options values

### Colors

The list of colors you can use in DevDash configuration.

Their display will depend of the colors you've configured for your terminal.

| Name    |
|---------|
| default |
| black   |
| red     |
| green   |
| yellow  |
| blue    |
| magenta |
| cyan    |
| white   |

### Size

DevDash is based on a 12 columns grid.

You can indicate the width of a widget in number of column (1 to 12), or using the equivalent t-shirt size as described below:

| Name   | Number of columns   |
| ------ | ------------------- |
| xxs    | 1                   |
| xs     | 2                   |
| s      | 4                   |
| m      | 6                   |
| l      | 8                   |
| xl     | 10                  |
| xxl    | 12                  |

### Time range

The `start_date` and `end_date` options accept dates following this format: `2016-01-02`.

You can use as well aliases relative to the present day.

The same alias can be a different date depending if it's used for the `start_date` or the `end_date` option. 

You can replace every `x` in the names by numerical values.

| Name           | start_date                                           | end_date                                            |
| -------------- | ---------------------------------------------------- | --------------------------------------------------- |
| today          | current day                                          | current day                                         |
| yesterday      | yesterday                                            | yesterday                                           |
| x_days_ago     | `x`th day before the current day                     | `x`th day before the current day                    |
|                |                                                      |                                                     |
| this_week      | first day of the actual week                         | last day of the actual week                         |
| last_week      | first day of the last week                           | last day of the last week                           |
| x_weeks_ago    | first day of the `x`th week before the current week  | last day of the `x`th week before the current week  |
|                |                                                      |                                                     |
| this_month     | first day of the actual month                        | last day of the actual month                        |
| last_month     | first day of the last month                          | last day of the last month                          |
| x_months_ago   | first day the `x`th month before the current month   | last day the `x`th month before the current month   |
|                |                                                      |                                                     |
| this_year      | first day of the actual year                         | last day of the actual year                         |
| last_year      | first day of the last year                           | last day of the last year                           |
| x_years_ago    | first day the `x`th year before the current year     | last day the `x`th year before the current year     |

# Acknowledgement

Thanks to [MariaLetta](https://github.com/MariaLetta/free-gophers-pack) for the awesome and beautiful Gopher pack she made! I used it for my logo on top.

DevDash was inspired from other open source projects:

* [wtf](https://github.com/wtfutil/wtf)
* [tdash](https://github.com/jessfraz/tdash)

# Contribute

First of all, thanks a lot if you want to contribute to DevDash!

I think the ["talk, then code"](https://dave.cheney.net/tag/contributing) practice is pretty good to avoid misunderstandings and hours of work for nothing.

Therefore:

"Every new feature or bug fix should be discussed with the maintainer(s) of the project before work commences. It’s fine to experiment privately, but do not send a change without discussing it first."

# Licence

[Apache Licence 2.0](https://choosealicense.com/licenses/apache-2.0/)
