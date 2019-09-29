---
title: General
weight: 1
---

This reference the general configuration for your dashboards.

| Name       | Description                                             | Default value   | Examples   |
| ---------- | ------------------------------------------------------- | --------------- | ---------- |
| refresh    | The cycle's duration of refreshing data, in seconds     | 600             | 600        |
| reload     | Hot reload the config file at each refresh              | false           | true       |

The reload option can be set to `true` if you want to change your dashboard without restarting it (hot reload).
This will allow you to change the dashboard configuration without the need to restart DevDash itself.

## Keystrokes

You can map some keystrokes to some action as following:

| Name | Description         | Default value | Examples   |
|------|---------------------|---------------|------------|
| quit | Key to quit DevDash | `C-c`         | `C-x`, `q` |

## Configuration Example

```yaml
general:
  refresh: 600
  keys:
    quit: "C-c"
```
