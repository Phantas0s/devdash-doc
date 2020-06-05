---
title: Host
weight: 2 
---

## Overview

This service can display Linux system information. You can grab them via SSH only if you have an SSH agent.

Some widgets might work as well on macOS.

## Service configuration

### Remote host

```yml
    services:
      remote_host:
         username: root
         address: "199.199.199.199:22"
```

### Local host

You don't need to configure any service. DevDash will fetch the data needed directly on your system.
You only need to replace every service ID from `rh` (remote host) to `lh` (local host) in the widget name.

## Widgets available

| Name                 | Description                                               |
| -------------------- | --------------------------------------------------------- |
| rh.box_uptime        | Total time the computer has been available                |
| rh.box_load          | CPU load                                                  |
| rh.box_cpu_rate      | CPU utilization (%)                                       |
| rh.box_memory_rate   | Memory utilization (%)                                    |
| rh.box_swap_rate     | Swap utilization (%)                                      |
| rh.box_net_io        | Network IO                                                |
| rh.box_disk_io       | Disk IO                                                   |
| rh.bar_memory        | Display memory information                                |
| rh.bar_rates         | Display CPU rate, memory rate and swap rate (see above)   |
| rh.table_disk        | Display information of different disks                    |
| rh.table             | Display whatever output from a command in a table         |


## Widget Options

### 


