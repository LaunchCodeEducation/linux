---
title: "Walkthrough"
date: 2022-03-02T09:54:08-06:00
draft: false
weight: 110
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

- listing unit files
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