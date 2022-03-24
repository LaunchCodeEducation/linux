---
title: "Python3 Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 110
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-16 # UPDATE ANY TIME CHANGES ARE MADE
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