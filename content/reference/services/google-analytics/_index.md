---
title: Google Analytics
weight: 4 
---

## Authorization

Obviously, you need to have a Google Analytics account or Google Search account to access these two services.

### Downloading the authorization JSON file 

(You don't need to repeat this step if you already did it when configuring Google Search Console)

1. Go to [Google APIs Credentials](https://console.developers.google.com/apis/api/webmasters.googleapis.com/credentials).
2. Select `Service account key`.
3. Create a new service account.
4. Select the role `Project -> Viewer` for a read access only.
5. Add a name.
6. Click on the button `create`.
7. Save the `Service account ID` somewhere. We will need it later.
8. Download the JSON file. **Its path need to be specified in the config of your DevDash dashboard.**

### Pulling data from Google Analytics

1. Go to your [Google Analytics account](https://search.google.com/search-console/users).
2. Click on `Admin` in the menu (last element of the menu)
3. Select the application you want to use with DevDash in the property column (just below the column name `property`).
4. Click on the `+` button and add a user.
5. Click on user management of the same column.
6. Enter the email address you saved before (the `Service account ID` of step 7, above).
7. Click on `View settings` on the `View` column and copy the `View ID` into your **DevDash configuration file**.

## Service configuration

```yml
    services:
      google_analytics:
        keyfile: goanalytics-abc123.json
        view_id: 456789123
```

## Widgets available

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

## Widget Options

### Bar Widgets

| Name            | Description                                                                    | Default value     | Examples                                 | Not available for                                        |
| --------------- | -----------------------------------------------------------------------------  | ----------------- | ---------------------------------------- | -------------------------------------------------------- |
| start_date      | Start date of time period                                                      | `7_days_ago`      | `2018-01-01`, `2_weeks_ago`              |                                                          |
| end_date        | End date of time period                                                        | `today`           | `2018-01-31`, `2_weeks_ago`              |                                                          |
| time_period     | Time period represented by a bar                                               | `days`            | `days`, `months`, `years`                |                                                          |
| metric          | Google analytics metric                                                        | `sessions`        | `page_views`, `bounces`, `entrances`     | `ga.bar_pages`, `ga.bar_returning`                       |
| dimensions      | Google analytics dimensions. Multiple value possible separated with a comma    |                   | `page_path`, `user_types`                | `ga.bar_pages`, `ga.bar_bounces`, `ga.bar_returning`     |
| filters         | Query filter (prefix `-` to exclude)                                           |                   | `value`, `-value`                        |                                                          |

### Table widgets

| Name            | Description                                                                    | Default value                                     | Examples                                     | Not used by                |
|-----------------|--------------------------------------------------------------------------------|---------------------------------------------------|----------------------------------------------|----------------------------|
| start_date      | Start date of time period                                                      | `7_days_ago`                                      | `2018-01-01`, `2_weeks_ago`                  |                            |
| end_date        | End date of time period                                                        | `today`                                           | `2018-01-31`, `2_weeks_ago`                  |                            |
| metrics         | Google analytics metrics. Multiple values possible separated with a comma      | `sessions,page_views,entrances,unique_page_views` | `bounces,sessions`, `entrances`              |                            |
| dimension       | Google analytics dimension                                                     | `page_path`                                       | `2018-01-31`, `2_weeks_ago`                  | `ga.table_traffic_sources` |
| orders          | Order of the result. Multiple value possible separated with a comma            | `sessions desc`                                   | `sessions desc,page_views asc`. `page_views` |                            |
| filters         | Query filter (prefix `-` to exclude)                                           |                                                   | `value`, `-value`                            |                            |
| row_limit       | Limit the number of rows                                                       | 5                                                 | 5, 100                                       |                            |
| character_limit | Limit the number of characters of the dimension column                         | 20                                                | 100, 200                                     |                            |

### Box widgets

| Name             | Description                                                                    | Default value   | Examples                               |
|------------------|--------------------------------------------------------------------------------|-----------------|----------------------------------------|
| start_date       | Start date of time period                                                      | `7_days_ago`    | `2018-01-01`, `2_weeks_ago`            |
| end_date         | End date of time period                                                        | `today`         | `2018-01-31`, `2_weeks_ago`            |
| metric           | Google analytics' metric                                                       | `sessions`      | `page_views`, `bounces`, `entrances`   |
