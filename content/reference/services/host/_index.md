---
title: Host
weight: 2 
---

## Overview

This service can display Linux system information for your local host or from remote hosts. 

If you want to grab information from a remote host, you need to fulfill these conditions:

1. You need your ssh key added to [ssh-agent](https://www.ssh.com/ssh/agent).
2. You need to be able to connect to the remote host [without password](https://www.ssh.com/ssh/copy-id).

Some widgets might work as well on macOS, but I don't guarantee it. I don't have macOS, so I can't test it.

## Service configuration

### Local host

You don't need to configure any service. DevDash will fetch the data needed directly on your system.
You only need to replace every service ID from `rh` (remote host) to `lh` (local host) in the widget name.

### Remote host

```yml
services:
  remote_host:
    username: my-cool-user
    address: "199.199.199.199:22"
```

The port `22` is important! Without it, it won't work.

## Widgets available

| Name                 | Description                                               |
| -------------------- | --------------------------------------------------------- |
| rh.box_uptime        | Total time the computer has been available                |
| rh.box_load          | CPU load (from boot)                                      |
| rh.box_net_io        | Network IO                                                |
| rh.box_disk_io       | Disk IO                                                   |
| rh.bar_memory        | Display memory information                                |
| rh.gauge_cpu_rate    | CPU utilization (%)                                       |
| rh.gauge_memory_rate | Memory utilization (%)                                    |
| rh.gauge_swap_rate   | Swap utilization (%)                                      |
| rh.bar_rates         | Display CPU rate, memory rate and swap rate (see above)   |
| rh.table_disk        | Display information of different virtual disks            |
| rh.box               | Display whatever output from a command in a text box      |
| rh.gauge             | Display whatever output from a command in a gauge diagram |
| rh.table             | Display whatever output from a command in a table         |
| rh.bar               | Display whatever output from a command in a bar diagram   |

## Widget Options

If these options are not provided, they will fall back to some default values.

### Option title

You can use the option `title` for every widget.

### Option unit

The option `unit` can convert an output in one unit to another. By default, if you don't precise the option, everything is converted to kilobit. You can convert from bit (`b`) to exabit(`eb`).

Widget supporting the options:

* `box_disk_io` 
* `box_net_io` 
* `bar_memory` 
* `table_disk` 

### Option command

This is a command line you can run to display the output in your dashboard. Pipes are supported, but not quotes for now. If you need to use them, just create a script and run it via this option.

Widget supporting the options:

* `rh.box`
* `rh.gauge`
* `rh.table`
* `rh.bar`

The output of the command line ran needs to be formatted as follow:

#### rh.box

The output of the command needs to be a string.

#### rh.gauge

The output of the command needs to be a percentage (a number less 100).

#### rh.table

Each line of the output represent one row in the table, and the string separated with a space will populate the cells.

You can provide headers with the options `headers`, for example: `headers: "first,second,third,fourth"`.

If no headers are provided, the first line of the output will be considered as headers.

#### rh.bar

You can provide  headers with the options `headers`, for example: `headers: "first,second,third,fourth"`. The number of headers need to match the number of bar you have in your diagram.

If the `headers` option is not provided, it will fall back to some dummy defaults. It won't be very useful...

The output of the command line needs to be a sequence of numbers, separated with spaces. Each number represent a bar in the diagram.

The numbers can be on multiple lines.
