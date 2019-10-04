---
title: General
weight: 1
---

This reference the general configuration for your dashboards.

| Name       | Description                                             | Default value   | Examples   |
| ---------- | ------------------------------------------------------- | --------------- | ---------- |
| refresh    | The cycle's duration of refreshing data, in seconds     | 600             | 600        |


## Keystrokes

You can map some keystrokes to some action as following:

| Name       | Description                                  | Default value   | Examples     |
| ------     | ---------------------                        | --------------- | ------------ |
| quit       | Key to quit DevDash                          | `C-c`           | `C-x`, `q`   |
| hot_reload | Key to hot reload your dashboard config file | `C-r`           | `C-x`, `q`   |

The hot reload key can be useful to modify your dashboard via the configuration file, without having to restart DevDash!

## Configuration Example

```yaml
general:
  refresh: 600
  keys:
    quit: "C-c"
    hot_reload: "C-r"
```
