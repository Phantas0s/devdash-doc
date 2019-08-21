---
title: Use Cases
weight: 1100
chapter: false
---

I use DevDash myself, so here my configurations to help you getting started creating your owns.

## A Wonderful Dashboard for Your Blog

Behold one of my dashboard for the blog [The Valuable Dev](https://thevaluable.dev) (formerly webtechno.net).

DevDash is good to have all the metrics you need for your blog, without having to go into the monstrous interface of Google Analytics.

Just configure what you want... and that's all!

{{%expand "Click to see the config" %}}
```yaml
---
general
  refresh: 600
  keys:
    quit: "C-c"

projects:
  - name: web-techno.net - Metrics
    title_options:
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
      google_search_console:
        keyfile: goanalytics-123.json
        view_id: 12345678
        address: 'https://web-techno.net'
    widgets:
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_users
                  options:
                    start_date: "15_days_ago"
                    end_date: "today"
                    bar_color: yellow
                    border_color: yellow
                    title_color: yellow
                    num_color: black
                    bar_gap: 1
                - name: ga.bar_users
                  options:
                    start_date: "12_months_ago"
                    end_date: "this_month"
                    time_period: month
                    title_color: red
                    border_color: red
                    bar_color: red
                    bar_width: 8
                    num_color: black
                    bar_gap: 1
          - col:
              size: "S"
              elements:
                - name: ga.bar_new_returning
                  options:
                    start_date: "6_months_ago"
                    end_date: "this_month"
                    time_period: month
                    metric: "users"
                    title_color: blue
                    bar_width: 8
                    num_color: black
                    bar_gap: 2
                    height: 20
          - col:
              size: "XS"
              elements:
                - name: ga.box_real_time
                  options:
                    title_color: red
                    border_color: red
                    text_color: red
                - name: mon.box_availability
                  options:
                    title_color: yellow
                    border_color: yellow
                    text_color: green
                    num_color: default
                - name: ga.box_total
                  options:
                    title: "sessions/users 4 weeks ago"
                    metric: "ga:sessionsPerUser"
                    title_color: green
                    border_color: green
                    text_color: green
                    num_color: default
                    start_date: 4_weeks_ago
                    end_date: 4_weeks_ago
                - name: ga.box_total
                  options:
                    title: "sessions/users 3 weeks ago"
                    metric: "ga:sessionsPerUser"
                    title_color: blue
                    border_color: blue
                    text_color: blue
                    num_color: default
                    start_date: 3_weeks_ago
                    end_date: 3_weeks_ago
                - name: ga.box_total
                  options:
                    title: "sessions/users 2 weeks ago"
                    metric: "ga:sessionsPerUser"
                    title_color: blue
                    text_color: magenta
                    border_color: magenta
                    num_color: default
                    start_date: 2_weeks_ago
                    end_date: 2_weeks_ago
                - name: ga.box_total
                  options:
                    title: "sessions/users 1 week ago"
                    metric: "ga:sessionsPerUser"
                    text_color: default
                    num_color: default
                    start_date: last_week
                    end_date: last_week
      - row:
          - col:
              size: "S"
              elements:
                - name: gsc.table_pages
                  options:
                    start_date: "last_week"
                    end_date: "last_week"
                    character_limit: 20
                    border_color: magenta
                    title_color: blue
                    row_limit: 10
                - name: ga.table_traffic_sources
                  options:
                    title: "Traffic sources - Today"
                    filters: "google"
                    start_date: "today"
                    end_date: "today"
                    first_color: red
                    second_color: yellow
                    row_limit: 8
          - col:
              size: "S"
              elements:
                - name: gsc.table_queries
                  options:
                    title: "Last week queries (-date, -php)"
                    start_date: "last_week"
                    end_date: "last_week"
                    character_limit: 25
                    row_limit: 19
                    border_color: magenta
                    title_color: blue
                    filters: "-date,-php"
                    # metrics: "clicks,ctr"
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - Yesterday"
                    start_date: "yesterday"
                    end_date: "yesterday"
                    border_color: magenta
                    title_color: blue
                    metrics: "sessions"
                    row_limit: 19
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - Today"
                    metrics: "sessions"
                    start_date: "today"
                    end_date: "today"
                    border_color: magenta
                    title_color: blue
                    row_limit: 19
```
{{% /expand%}}

![img](/img/screenshot/mix-1.png)
