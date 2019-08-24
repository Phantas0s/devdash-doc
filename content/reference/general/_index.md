---
title: General
weight: 1
---

General configuration of your dashboard.

| Name     | Description                                           | Default value | Examples |
|----------|-------------------------------------------------------|---------------|----------|
| refresh  | The cycle's duration of refreshing data, in seconds   | 600           | 600      |

## Keys

You can map some keyboard key to some action as following:

| Name | Description         | Default value | Examples   |
|------|---------------------|---------------|------------|
| quit | Key to quit DevDash | `C-c`         | `C-x`, `q` |

## Example

```yaml
general:
  refresh: 600
  keys:
    quit: "C-c"
```
