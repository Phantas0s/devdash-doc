---
title: Projects
weight: 10
---

A `project` in devdash is simply an high level entity which has a displayed title, a bunch of services and widgets.

You can have one or multiple project per dashboard.

For example:

```YAML
projects:
  - name: DevDash
    name_options:
      border_color: default
      text_color: default
      size: XXL
      bold: true
    services:
      github:
        token: 1234
        owner: Phantas0s
        repository: devdash
    themes:
      bar:
        title_color: red
      table:
        border_color: green
      ocean:
        bar_gap: 1
```
## Name

The name, displayed on the DevDash dashboard as a simple `box` widget.

## Name Options

You can precise there some display options for the project's name.

| Name             | Description                               | Default value               | Examples                                    |
| ---------------- | ----------------------------------------- | --------------------------- | ------------------------------------------- |
| border_color     | Border color                              | `Default color`             | [colors](/display/colors)                   |
| text_color       | Text color                                | `Default color`             | [colors](/display/colors)                   |
| size             | Width of the name                         | `12`                        | [sizes](/display/size)                      |
| bold             | Display the title in bold characters      | `true`                      | `true`, `false`                             |
## Services

The configuration of your services will be done in the `services` section of the project's configuration. [You can find service's configuration reference here](/reference/services/).

## Themes

To have a concrete example of a dashboard with themes, [it's over there](/getting-started/use-cases/devdash/).

You can create themes which will be applied to [different type of widgets](/display/widgets/) automatically.

For example:

```yaml
projects:
  - name: project1
    themes:
      bar:
        title_color: green
        border_color: green
        text_color: green
        num_color: magenta
      table:
        title_color: red
        border_color: red
        text_color: red
        num_color: green
      box:
        title_color: yellow
        border_color: yellow
        text_color: yellow
        num_color: red
```

You can as well create themes and attach them to some widgets: 

```yaml
projects:
  - name: project1
    services:
      google_analytics:
        keyfile: goanalytics-123.json
        view_id: 12345678
    themes:
      my-theme:
        start_date: "15_days_ago"
        end_date: "today"
        bar_color: yellow
        border_color: yellow
        title_color: yellow
        num_color: black
        bar_gap: 1
    widgets:
      - row:
          - col:
              size: "M"
              elements:
                - name: ga.bar_users
                  theme: my-theme
```

As you can see, you don't have to precise only display related option in your theme: you can just add any widget option you want.

Themes are very useful if you want the same options for different widgets without the need to copy the same options in every single one of them. 

