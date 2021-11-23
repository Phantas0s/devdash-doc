---
title: Installation
weight: 15
---

## General

You can simply grab the [latest released binary file](https://github.com/Phantas0s/devdash/releases/latest) and download the version you need, depending on your OS.

## Linux script

Here's a simple way to download DevDash and move it in `/usr/local/bin`, in order to be able to use DevDash everywhere easily.

```shell
curl -LO https://raw.githubusercontent.com/Phantas0s/devdash/master/install/linux.sh && \
sh ./linux.sh && \
rm linux.sh
```

## Manual installation

You need to clone this repository and build the binary in `cmd/devdash`.
