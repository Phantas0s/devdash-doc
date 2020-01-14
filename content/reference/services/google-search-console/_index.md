---
title: Google Search Console
weight: 6 
---

## Authorization

### Downloading the authorization JSON file 

(You don't need to repeat this step if you already did it when configuring Google Analytics)

1. Go to [Google APIs Credentials](https://console.developers.google.com/apis/api/webmasters.googleapis.com/credentials).
2. Select `Service account key`.
3. Create a new service account.
4. Select the role `Project -> Viewer` for a read access only.
5. Add a name.
6. Click on the button `create`.
7. Save the `Service account ID` somewhere. We will need it later.
8. Download the JSON file. **Its path need to be specified in the config of your DevDash dashboard.**

### Pulling data from Google Search Console

1. Go to your [Google Search Console account](https://search.google.com/search-console/)
2. Click the property you want to access with DevDash.
3. Click on `Settings` in the menu on the left.
4. Click on `Users and permissions` and add a user with the `Service Account ID` as email address (see step 7 of `Downloading the authorization JSON file` above).

## Service configuration

```yml
    services:
      google_search_console:
        keyfile: goanalytics-abc123.json
```

## Widgets available

| Name                | Description                                                                             |
| ------------------- | --------------------------------------------------------------------------------------- |
| gsc.table_pages     | Display clicks, impressions, ctr, position for pages                                    |
| gsc.table_queries   | Display clicks, impressions, ctr, position for queries                                  |
| gsc.table            | Display theoretically any dimension from Google Search Console on a given time period   |

## Widget Options

### Table widgets

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
