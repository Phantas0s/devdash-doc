---
title: Installation
weight: 15
---

## General

You can use any dashboard you've configured by using the command `devdash -c <dashboard>`.

To see how to create a dashboard configuration, [it's over there](/getting-started/quick-start/).

## Available Commands

You can run `devdash help` or `devdash <my_command> --help` (for example `devdash edit --help`) for more information.

* `devdash list` - List all your dashboards.
* `devdash generate` - Generate a DevDash template.
    * It will prompt you to fill some field; you can let them blank if you want.
    * The option `-t` (for `t`ype) can let you choose the template you want.
    * Possible type of template: "blog" or "project" (for a Github project).
* `devdash` - Open the dashboard `$XDG_CONFIG_HOME/devdash/default.yml`. To precise another dashboard, use the option `-c` without the file extension. For example `devdash -c my_dashboard`.
* `devdash edit` - Edit the dashboard `$XDG_CONFIG_HOME/devdash/default.yml`.
    * To precise another dashboard, you can run `devdash edit my_dashboard.yml`.
    * The editor set to the environment variable `$EDITOR` is used by default. 
    * If you want to use another editor, you can use the option `-e` followed by your editor. For example: `-e nano` or `-e /usr/bin/nano`.
* `devdash version` - Output the current version.
