---
title: Quick Start
weight: 20
---

To see DevDash in action and get familiar with the config file, you can easily configure the monitoring service as following:

![img](/img/screenshot/monitor.png)

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

Note that you can write the config in JSON, too. Here's an example:

```json
{
  "projects": [
    {
      "name": "Quickstart",
      "services": {
        "monitor": {
          "address": "https://thevaluable.dev"
        }
      },
      "widgets": [
        {
          "row": [
            {
              "col": {
                "size": "M",
                "elements": [
                  {
                    "name": "mon.box_availability",
                    "options": {
                      "border_color": "green"
                    }
                  }
                ]
              }
            }
          ]
        }
      ]
    }
  ]
}
```

Every config in this documentation are written in YAML. Feel free to convert them using a tool [like this one](https://onlineyamltools.com/convert-yaml-to-json) if you want some JSON.

I would advise you to create a folder where you could create as many DevDash dashboard as you need.

For example:

* Copy past the above config in a new file (`monitoring.yml`, for example)
* Run DevDash: `devdash -config monitoring.yml`

Congratulation! You just created your first dashboard. DevDash will simply send a request every `600` seconds to `https://thevaluable.dev` (my blog) and display the response's status code.

To see the power of DevDash, you can see some [simple example of configurations here](/getting-started/examples/).
