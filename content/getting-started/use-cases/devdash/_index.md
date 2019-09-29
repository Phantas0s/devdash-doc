---
title: DevDash
---

I use this dashboard to monitor DevDash on Github, especially when I write about it on social media.

{{%expand "I want the config!" %}}
```YAML
---
projects:
  - name: DevDash
    services:
      github:
        token: 1234
        owner: Phantas0s
        repository: devdash
    themes:
      bar:
        # Everything is yellow except the title color / bar color.
        color: yellow
        title_color: red
        bar_color: green
        bar_gap: 1
      table:
        border_color: green
        row_limit: 10
      ocean:
        border_color: blue
        num_color: black
        bar_color: cyan
        title_color: magenta
        bar_gap: 1

    widgets:
      - row:
          - col:
              size: 12
              elements:
                # The widget is of type "bar": the theme bar is applied.
                - name: github.bar_stars
      - row:
          - col:
              size: 6
              elements:
                - name: github.bar_views
                  # The theme "ocean" override the theme "bar".
                  theme: ocean
                  options:
                    height: 23
                    bar_gap: 5
                    bar_width: 6
          - col:
              size: 6
              elements:
                # The theme table is applied
                - name: github.table_repositories
      - row:
          - col:
              size: 12
              elements:
                # The theme bar is applied
                - name: github.bar_commits
                  options:
                    start_date: 35_weeks_ago
```
{{% /expand%}}

![devdash github dashboard](/img/screenshot/devdash-1.png)
