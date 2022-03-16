---
title: "Listing Unit Files"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 100
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-16 # UPDATE ANY TIME CHANGES ARE MADE
---

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