---
title: Installation
weight: 20
---

## General

You can simply grab the [latest released binary file](https://github.com/Phantas0s/devdash/releases/latest) and download the good version, depending on your OS.

## Linux script

Here's a simple way to download and put DevDash in `/usr/local/bin`, which should be part of your path.

```shell
curl -LO https://raw.githubusercontent.com/Phantas0s/devdash/master/install/linux.sh && \
sh ./linux.sh && \
rm linux.sh
```

## Manual installation

You need go installed to compile DevDash.

Then, simply run `go get -u github.com/Phantas0s/devdash/cmd/devdash`

