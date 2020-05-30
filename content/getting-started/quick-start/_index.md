---
title: Quick Start
weight: 20
---

To see DevDash in action and get familiar with the config file, you can simply launch devdash. This is what you'll see:

![img](/img/screenshot/monitor.png)

If you don't provide any dashboard configuration file, DevDash will automatically create one located at `$HOME/.config/devdash/default.yml`.

You can open it in your favorite editor and modify it as much as you want:

```yml
---
general:
  refresh: 600
  keys:
    quit: "C-c"
    hot_reload: "C-r"

projects:
  - name: Default dashboard located at $HOME/.config/devdash/default.yml
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
                    title: " thevaluable.dev status "
                    color: yellow`
```

This tells DevDash to send a request every `600` seconds to `https://thevaluable.dev` (my blog) and display the response's status code. You can monitor your own website, or even Google if you want, by replacing the address.

If you create a new dashboard in this folder, say `my_dashboard.yml`, DevDash can find it if you only give it the name: `devdash -c my_dashboard`. In general, to find a dashboard, DevDash will look in these directories, in that order:

* The current directory you're in.
* $XDG_HOME_CONFIG/devdash/
* $HOME/.config/devdash/

You can as well give DevDash an absolute path as follow: `devdash -c ~/.config/devdash/default.yml`.

To see the power of DevDash, you can look at some [simple example of configurations here](/getting-started/examples/).
