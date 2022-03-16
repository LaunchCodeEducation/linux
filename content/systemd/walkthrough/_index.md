---
title: "Walkthrough"
date: 2022-03-02T09:54:08-06:00
draft: false
weight: 110
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

- simple unit files
  - bash scripts
  - python3 scripts
  - node scripts
- `systemctl`
  - `status`
  - `start`
  - `stop`
  - `enable`
  - `disable`
- `journalctl`
- webserver unit files
  - caddy
  - nginx
- database unit file
- webapp (non-persistent) until files
  - static
  - reverse proxy
- webapp (persistent) unit files
  - depends on database service
  - reverse proxy

## Walkthrough

{{% children %}}