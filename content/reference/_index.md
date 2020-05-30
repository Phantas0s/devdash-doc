+++
title = "Configuration Reference"
weight = 5
pre = "<b>2. </b>"
draft = false
+++

You will find here an exhaustive reference for every options you can use in DevDash configurations, for every `project`, `service` and `widget`.

This section will explain:

* The highest configuration level, namely the [general options](/reference/general/) for your dashboard. 
* The second level is the `project` configuration, where you will configure its title and declare its `services`.
* The third and fourth levels are the configuration of the `services` themselves and their `widgets`.

If you're unsure how a configuration file should look like, you can look at simple configuration [examples](/getting-started/examples). You can as well find real life [use-cases](/getting-started/use-cases) with their complete dashboard configurations.

Many screenshot are included for you to see directly how DevDash can look like.

## Loading a Configuration

By default, devdash will search for a dashboard configuration in these folder, in that order:

* The current directory you're in
* `$XDG_HOME_CONFIG/devdash/`
* `$HOME/.config/devdash/`

You can display your dashboard as follow: `devdash -c <dashboard_name>`. You can give an absolute path instead of a filename, too.

## DevDash Widgets

Each widget depend on a service: the name of the widget will determine the service links to it.

For example, the widget `ga.bar_pages` will belong to the service `google_analytics` (`ga`).

Here are the different services you can find in the widget's names:

| Identifier | service               |
| ------     | --------------------- |
| ga         | Google Analytics      |
| gsc        | Google Search Console |
| github     | Github                |

The second part of the widget name, `bar` in `ga.bar_pages` determine the widget `type`.

## DevDash Configuration Structure

This schema illustrate the different levels a DevDash configuration has.

* A dashboard can have one or multiple `projects`. The name of the `project` will be displayed on the dashboard.
* A project can have one or multiple `services`. Often a service will require `authorization credentials` or other information many `widgets` possibly use.
* The `widgets` are linked to `services`. These `widgets` needs to be positioned following a grid with `rows` and `columns`.

![schema of DevDash configuration](/img/struct.png)
