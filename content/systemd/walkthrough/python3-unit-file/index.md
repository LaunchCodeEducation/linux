---
title: "Python3 Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
hidden: true
weight: 120
---

real handy command: `systemctl list-units --type target`

```bash
[Unit]
Description=Keystroke logger

[Service]
ExecStart=/usr/local/pylogger/env_pylogger/bin/python3 /usr/local/pylogger/main.py
Restart=on-failure

[Install]
WantedBy=multi-user.target
# WantedBy=graphical.target
```

- have students clone [lc-pylogger](https://github.com/LaunchCodeTechnicalTraining/lc-pylogger)
- have students create a virtualenv for project
- have students run program with virtualenv
- walk students through creating the very simple unit file using virtualenv and executing lc-pylogger
- `systemctl start [unit-name.service]`
- `systemctl stop [unit-name.service]`

Now the key-logger can be started or stopped with the `systemctl` tool.