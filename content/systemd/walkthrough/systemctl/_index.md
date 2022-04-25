---
title: "systemctl"
weight: 100
date: 2022-04-18
---

`systemd` isn't touched by the end user directly. End user's work with `systemd` by using the `systemctl` package and by defining `systemd unit files`.

`systemctl` gives the end user access to information and control over all services, daemons, and unit files.

Knowing some of the basic commands of `systemctl` is necessary for working with services.

## Status

> Show terse runtime status information about one or more units, followed by most recent log data from the journal.

```bash
systemctl status nginx
```

The `status` command displays the current status of a specific service.

## Start

> Start (activate) one or more units specified on the command line.

```bash
sudo systemctl start nginx
```

The `start` command starts a service.

## Stop

> Stop (deactivate) one or more more units specified on the command line.

```bash
sudo systemctl stop nginx
```

The `stop` command stops a service.

## Enable

> Enables one or more units... ...Enabling simply hooks the unit into various suggested places (for example, so that the unit is automatically started on boot or when a particular kind of hardware is plugged in).

```bash
sudo systemctl enable nginx
```

The `enable` command will automatically start a service at a specific computer runtime target. For example a service may be configured to start when the computer boots.

## Disable

> Disables one or more units.

```bash
sudo systemctl disable nginx
```

The `disable` command will not automatically start a service at a specific computer runtime target.

## Listing Units

```bash
systemctl list-units
```

All units can be listed with the `list-units` command.

In the following articles we will explore the Caddy and NGINX unit files that were automatically created when those tools were installed on the computer.