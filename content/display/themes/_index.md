---
title: Themes
weight: 1 
---

A theme is a blueprint for any widget. It can have any option and can be reused across widgets.

For example:

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
```

The themes with the name `ocean` can be used for any widget, as following:

```YAML
- row:
    - col:
        size: 6
        elements:
        - name: github.bar_views
          theme: ocean
```

The widget `github.bar_views` will inherit the options defined by the theme `ocean`.

A theme can have reserved names: `bar`, `table` and `box`. These are the names of the different widget types in Devdash, too.

If a theme has one of these reserved name, every widget of the type will inherit the theme's options. For example, if you have a theme `bar`, every `bar` widget will have the options of the theme.

If the widget and the widget's theme have options in common, the widget's options will override the ones from the theme.
