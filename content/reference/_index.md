+++
title = "Configuration Reference"
weight = 5
pre = "<b>2. </b>"
draft = false
+++

You will find here a precise reference of every options you can use in DevDash's configurations, for every `project`, `service` and `widget`.

You can find here: 

* The highest configuration level, namely the [general options](/reference/general/) for your dashboard. 
* The second level is the `project` configuration: it's where you will give its title and declare its `services`.
* The third and fourth levels are the configuration of the `services` themselves and their `widgets`.

If you're unsure how should looks like a configuration file, you can go to the section [getting started](/getting-started/), and more particularly in its subsections [examples](/getting-started/examples) for simple configuration examples. You will find there as well real life [use-cases](/getting-started/uses-cases) with their complete dashboard configurations.

Many screenshot are included for you to see directly how DevDash can look like.

## DevDash Widgets

Each widget depend on a service: the name of the widget will determine in what service it belongs.

For example, the widget `ga.bar_pages` will belong to the service `google_analytics`.

Here the different services you can find in the widget's names:

| Identifier | service               |
| ------     | --------------------- |
| ga         | Google Analytics      |
| gsc        | Google Search Console |
| github     | Github                |

The second part of the widget name, `bar` in `ga.bar_pages` determine its display. 

## DevDash Configuration Structure

This schema illustrate the different level a DevDash configuration has.

* A dashboard can have one or multiple `projects`. The name of the `project` will be displayed on the dashboard.
* A project can have one or multiple `services`. Often a service will require `authorization credentials` or other information many `widgets` possibly use.
* `Services` can display one or multiple `widgets`. These `widgets` needs to be positioned on `rows` and `columns`, following a grid.

![schema of DevDash configuration](/img/struct.png)
