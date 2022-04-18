---
title: "systemctl"
weight: 100
date: 2022-04-18
---

`systemd` isn't touched by the end user directly. End user's work with `systemd` by using the `systemctl` package and by defining `systemd unit files`.

`systemctl` gives the end user access to information and control over all services, daemons, and unit files.

Knowing some of the basic commands of `systemctl` is necessary for working with services and daemons.

## Status

## Start

## Stop

## Enable

## Disable

## Listing Units

## Listing Unit Files

- `systemctl`
  - `--help`
  - `systemctl list-units`
  - `systemctl list-dependencies [UNIT...]`
  - `systemctl list-unit-files [PATTERN...]`
    - `systemctl list-unit-files accounts-daemon.service`
    - `sudo find / -name "accounts-daemon.service"`
      - `/usr/lib/systemd/system/accounts-daemon.service`
      - `/sys/fs/cgroup/pids/system.slice/accounts-daemon.service`
      - `/var/lib/systemd/deb-systemd-helper-enabled/graphical.target.wants/accounts-daemon.service`
      - `/etc/systemd/system/graphical.target.wants/accounts-daemon.service`
    - `systemctl list-unit-files apt-daily.service`
      - `sudo find / -name "apt-daily.service`
        - `/usr/lib/systemd/system/apt-daily.service`
        - `find: '/run/user/1000/gvfs': Permission denied`
        - `cat /usr/lib/systemd/system/apt-daily.service`
          - `cat /usr/lib/apt/apt.system.daily` --> it's a dash script! --> that's all it is, this script is executed after the dependencies are satisfied, and it only fires once (oneshot)
    - `systemctl list-units --status=active`
      - `systemctl status colord.service`
      - `sudo find / -name colord.service`
        - `cat /usr/lib/systemd/system/colord.service`
        - `Description=Manage, Install and Generate Color Profiles`
        - `ExecStart=/usr/libexec/colord`
        - `cat /usr/libexec/colord` --> it's a binary
        - `ls -l /usr/libexec | grep colord`