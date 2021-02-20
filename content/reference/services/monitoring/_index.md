---
title: Monitoring
weight: 1
---

## Service configuration

```yml
    services:
      monitor:
        address: "https://www.my-website.net"
```

## Widgets available

| Name                     | Description                                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| mon.box_availability     | Send an HTTP request to the address specified in he service configuration and display the response's status code   |

## Widget Options

### Box Widgets

| Name      | Description                    | Example                  |
| --------- | ------------------------------ | ------------------------ |
| address   | Override the service's address | https://www.google.com   |
