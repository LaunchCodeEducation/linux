---
title: "systemctl"
weight: 100
date: 2022-04-18
---

`systemd` isn't touched by the end user directly. End user's work with `systemd` by using the `systemctl` package and by defining `systemd unit files`.

`systemctl` gives the end user access to information and control over all services, daemons, and unit files.

Knowing some of the basic commands of `systemctl` is necessary for working with services and daemons.

## Status

> Show terse runtime status information about one or more units, follwoed by most recent log data from the journal.

```bash
systemctl status nginx
```

## Start

> Start (activate) one or more units specified on the command line.

```bash
sudo systemctl start nginx
```

## Stop

> Stop (deactivate) one mor more units specified on the command line.

```bash
sudo systemctl stop nginx
```

## Enable

> Enables one or more units... ...Enabling simply hooks the unit into various suggested places (for example, so that the unit is automatically started on boot or when a particular kind of hardware is plugged in).

```bash
sudo systemctl enable nginx
```

## Disable

> Disables one or more units.

```bash
sudo systemctl disable nginx
```

## Listing Units

```bash
systemctl list-units
```