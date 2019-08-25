---
title: Examples
weight: 1000
---

Here are some simple examples to get you started. If you need more complex and real use cases, it's [over there](/getting-started/use-cases/).

## Google Analytics

There are two services used here: the [monitoring service](/reference/services/monitoring/) and the [Google Analytics service](/reference/services/google-analytics/).

This first simple example show you how to use two different way or providing the [size](/display/size/) (width) of any widget ("6", "S" and "XS").

As you can see, you need to provide a `keyfile` and a `view_id` for the service `google_analytics`. There is a walkthrough how to obtain these two information [here](/reference/services/google-analytics/).

{{%expand "Show me the config!" %}}
```yaml
---
projects:
  - name: Example
    name_options:
      border_color: default
      text_color: default
      size: XXL
      bold: true
    services:
      google_analytics:
        keyfile: goanalytics-123.json
        view_id: 12345678
      monitor:
        address: "https://www.web-techno.net"
    widgets:
      - row:
          - col:
              size: "6"
              elements:
                - name: ga.bar_users
                  options:
                    title: "Example bar widget 1"
                    start_date: "15_days_ago"
                    end_date: "today"
                - name: ga.bar_users
                  options:
                    start_date: "12_months_ago"
                    end_date: "this_month"
                    title: "Example bar widget 2"
          - col:
              size: "S"
              elements:
                - name: ga.bar_new_returning
                  options:
                    title: "Example bar widget 3"
                    start_date: "3_days_ago"
                    end_date: "today"
                    metric: "users"
                    height: 20
          - col:
              size: "XS"
              elements:
                - name: ga.box_real_time
                - name: mon.box_availability
                - name: ga.box_total
                  options:
                    startDate: today
                    endDate: today
                    metric: "users"
```
{{% /expand%}}

![img](/img/screenshot/ga-1.png)

-------

The second example shows you how to configure the display of your widgets, using options like `border_color`, `text_color`, `bar_width` or `bar_height`. 

It introduces as well the `general` configuration, where you can provide the keys to use to quit devdash (`C-c` is ctrl-c) as well as the refresh cycle of your entire dashboard, in seconds.

You can see a [complete reference of these properties here](/display/widgets/).

{{%expand "Show me the config!" %}}
```yaml
---
general:
  refresh: 600
  keys:
    quit: "C-c"

projects:
  - name: Example
    services:
      google_analytics:
        keyfile: goanalytics-123.json
        view_id: 12345678
    widgets:
      - row:
          - col:
              size: "6"
              elements:
                - name: ga.bar_users
                  options:
                    title: "Example bar widget 1"
                    start_date: "3_months_ago"
                    end_date: "this_month"
                    time_period: month
                    border_color: red
                    text_color: yellow
                    bar_width: 10
                    bar_gap: 5
          - col:
              size: M
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - Yesterday"
                    start_date: "yesterday"
                    end_date: "yesterday"
                    metrics: "sessions"
                    character_limit: 10
                    row_limit: 2
      - row:
          - col:
              size: "XXL"
              elements:
                - name: ga.table_traffic_sources
                  options:
                    title: "Traffic sources - Today"
                    start_date: "today"
                    end_date: "today"
                    row_limit: 8
      - row:
          - col:
              size: M
              elements:
                - name: ga.table_pages
                  options:
                    title: "Bounces - Yesterday"
                    start_date: "yesterday"
                    end_date: "yesterday"
                    metrics: "ga:bounces"
                    character_limit: 10
                    row_limit: 2
```
{{% /expand%}}

![img](/img/screenshot/ga-2.png)


## Google Search Console

The Google Search Console service in action! If you want a [complete reference of its widget and configuration, click here](/reference/services/google-search-console/).

{{%expand "Show me the config!" %}}
```YAML
---
general:
  refresh: 600
  keys:
    quit: "C-c"

projects:
  - name: https://web-techno.net
    title_options:
      border_color: green
      text_color: yellow
      size: L
      bold: true
    services:
      google_search_console:
        keyfile: goanalytics-123.json
        address: 'https://web-techno.net'
    widgets:
      - row:
          - col:
              size: 12
              elements:
                - name: gsc.table_queries
                  options:
                    title: " Last month queries "
                    start_date: "last_month"
                    end_date: "last_month"
                    character_limit: 25
                    row_limit: 10
                    metrics: "clicks,impressions"
                    border_color: green
                    title_color: green
                    text_color: green
      - row:
          - col:
              size: 12
              elements:
                - name: gsc.table_pages
                  options:
                    title: " Last month pages "
                    start_date: "last_month"
                    end_date: "last_month"
                    character_limit: 25
                    row_limit: 10
                    border_color: yellow
                    title_color: yellow
                    text_color: yellow
```
{{% /expand%}}

![img](/img/screenshot/gsc-1.png)

## Github 

Bring your Github data in DevDash! [Click here to see the whole configuration reference](/reference/services/github/).

{{%expand "Show me the config!" %}}
```yaml
---
projects:
  - name: github
    name_options:
      border_color: default
      text_color: default
      size: XXL
      bold: true
    services:
      github:
        token: 123456789abcde12345av
        owner: Phantas0s
        repository: .dotfiles
    widgets:
      - row:
          - col:
              size: 12
              elements:
                - name: github.table_repositories
                  options:
                    metrics: stars,forks
                    row_limit: 5
                    title_color: blue
                    text_color: yellow
                    border_color: yellow
                    order: created
                - name: github.table_repositories
                  options:
                    row_limit: 5
                    title_color: blue
                    text_color: magenta
                    border_color: magenta
                - name: github.table_branches
                  options:
                    row_limit: 3
                    title_color: blue
                    text_color: green
                    border_color: green
                - name: github.table_issues
                  options:
                    row_limit: 10
                    title_color: blue
                    text_color: red
                    border_color: red
```
{{% /expand %}}

