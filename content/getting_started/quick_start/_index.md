---
title: Quick Start
weight: 20
---

To see DevDash in action and get familiar with the config file, you can easily configure the monitoring service:

![img](/img/screenshot/monitor.png)

Here the config to create this (very simple) dashboard:

```yml
---
projects:
  - name: Quickstart
    services:
      monitor:
        address: "https://www.web-techno.net"
    widgets:
      - row:
          - col:
              size: "M"
              elements:
                - name: mon.box_availability
                  options:
                    border_color: green
```

You can: 

* Copy past the config in a new file (`monitoring.yml`, for example)
* Run DevDash: `devdash -config monitoring.yml`

Congratulation! You just created your first dashboard. DevDash will simply send a request every `600` seconds to `https://www.web-techno.net` and display the response's status code.

