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
    - todo-api-spring: https://github.com/LaunchCodeTechnicalTraining/spring-todo-api
      - `git clone https://github.com/LaunchCodeTechnicalTraining/spring-todo-api`
      - `sudo apt install openjdk-11`
      - `/home/student/todo-api-spring/gradlew -p /home/student/todo-api-spring/ bootRun`
      - test with curl
        - `curl localhost:8080/todos`
        - `curl -XPOST localhost:8080/todos -H "Content-Type: application/json" -d '{"text": "dishes"}'`
        - `curl -XPOST localhost:8080/todos -H "Content-Type: application/json" -d '{"text": "laundry"}'`
        - `curl -XPOST localhost:8080/todos -H "Content-Type: application/json" -d '{"text": "wash car"}'`
        - `curl localhost:8080/todos`
        - 

- webapp (persistent) unit files
  - depends on database service
  - reverse proxy

## Walkthrough

{{% children %}}