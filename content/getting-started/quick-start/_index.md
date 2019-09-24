---
title: Quick Start
weight: 20
---

To see DevDash in action and get familiar with the config file, you can easily use the monitoring service:

![img](/img/screenshot/monitor.png)

Here's the config to create this (very simple) dashboard:

```yml
---
projects:
  - name: Quickstart
    services:
      monitor:
        address: "https://thevaluable.dev"
    widgets:
      - row:
          - col:
              size: "M"
              elements:
                - name: mon.box_availability
                  options:
                    border_color: green
```

I would advise you to create a folder wherever you want and stock in there every DevDash dashboard you need.

For example:

* Copy past the config in a new file (`monitoring.yml`, for example)
* Run DevDash: `devdash -config monitoring.yml`

Congratulation! You just created your first dashboard. DevDash will simply send a request every `600` seconds to `https://thevaluable.dev` (my blog) and display the response's status code.

These requests will be ignored by Google Analytics.

To see the power of DevDash, you can browse [simple example of configurations here](/getting-started/examples/).
