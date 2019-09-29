---
title: Projects
weight: 10
---

A `project` in devdash is simply an high level entity which has a displayed title, a bunch of services and some widgets.

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

The configuration of your services will be done in the `services` section of the project's configuration. [You can find service's configuration referenced here](/reference/services/).

## Themes

To have a concrete example of a dashboard with themes, [it's over there](/getting-started/use-cases/devdash/).

There is a [entire section devoted to theme here](/display/themes/).
