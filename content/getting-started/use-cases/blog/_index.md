---
title: Blog
weight: 1100
chapter: false
---

Behold some dashboards I have for my blog [The Valuable Dev](https://thevaluable.dev) (formerly webtechno.net).

DevDash is good to have all the metrics you need for your blog, without having to go into the monstrous interface of Google Analytics.

Just configure what you want... and that's all!

For information, I run all these dashboards at the same time all day long, with a refresh occurring every 10 minutes without any problem.

### General Dashboard

{{%expand "I want the config!" %}}
```YAML
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

### Page Dashboard
{{%expand "I want the config!" %}}
```YAML
---
projects:
  - name: https://thevaluable.dev - Pages
    services:
      google_analytics:
        keyfile: goanalytics-123.json
        view_id: 12345678
    widgets:
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    start_date: "18_days_ago"
                    end_date: "today"
                    filters: "/programming-project-ideas-personal-generation/"
          - col:
              size: "M"
              elements:
                # This widget is equivalent to bar_page. You can personalize your query to the API with ga.bar or ga.table.
                - name: ga.bar
                  options:
                    title: "DevDash Case Study"
                    color: cyan
                    start_date: "18_days_ago"
                    end_date: "today"
                    dimensions: "page_path"
                    metric: "page_views"
                    filters: "/programming-side-project-example-devdash/"
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Developer stress"
                    color: blue
                    start_date: "18_days_ago"
                    end_date: "today"
                    filters: "/developer-stress/"
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Anemic domain model"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: green
                    filters: "/anemic-domain-model/"
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Side Project Tools"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: yellow
                    border_color: default
                    filters: "/side-project-tools-practices/"
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Side Project Mindset"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: red
                    filters: "/side-project-successful/"
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Vim Search"
                    start_date: "18_days_ago"
                    end_date: "today"
                    # You can choose different colors for different element of a widget.
                    title_color: green
                    border_color: yellow
                    bar_color: red
                    filters: "/vim-search/"
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Mysql Command Line"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: blue
                    filters: "/mysql-command-line-tool-mycli/"
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Easy Just Simple"
                    start_date: "18_days_ago"
                    end_date: "today"
                    # This is equivalent to color: white.
                    title_color: white
                    border_color: white
                    bar_color: white
                    filters: "/development-easy-just-simple/"
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Vim PHP IDE"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: yellow
                    filters: "/vim-php-ide/"
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Dry Principle"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: red
                    filters: "/dry-principle-explained/"
          - col:
              size: "M"
              elements:
                - name: ga.bar_pages
                  options:
                    title: "Learn programming language"
                    start_date: "18_days_ago"
                    end_date: "today"
                    color: green
                    filters: "/how-to-learn-a-programming-language/"
```
{{% /expand%}}

![img](/img/screenshot/thevaluabledev-2.png)

### Page Comparison Dashboard

{{%expand "I want the config!" %}}
```YAML
---
projects:
  - name: https://thevaluable.dev - General
    services:
      google_analytics:
        keyfile: goanalytics-123.json
        view_id: 12345678
    widgets:
      - row:
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - 35 weeks ago"
                    start_date: "35_days_ago"
                    end_date: "35_days_ago"
                    color: default
                    metrics: "sessions"
                    row_limit: 30
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - 4 days ago"
                    start_date: "4_days_ago"
                    end_date: "4_days_ago"
                    color: red
                    metrics: "sessions"
                    row_limit: 30
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - 3 days ago"
                    start_date: "3_days_ago"
                    end_date: "3_days_ago"
                    color: yellow
                    metrics: "sessions"
                    row_limit: 30
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - 2 days ago"
                    start_date: "2_days_ago"
                    end_date: "2_days_ago"
                    color: blue
                    metrics: "sessions"
                    row_limit: 30
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - 1 days ago"
                    start_date: "yesterday"
                    end_date: "yesterday"
                    color: magenta
                    metrics: "sessions"
                    row_limit: 30
          - col:
              size: "XS"
              elements:
                - name: ga.table_pages
                  options:
                    title: "Pages - today"
                    start_date: "today"
                    end_date: "today"
                    color: green
                    metrics: "sessions"
                    row_limit: 30
```
{{% /expand%}}

![img](/img/screenshot/thevaluabledev-3.png)
