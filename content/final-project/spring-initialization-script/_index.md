---
title: "Spring Initialization Script"
weight: 110
date: 2022-05-05
---

## Get Organized

What needs to happen for the Spring project to be deployed?

### VirtualBox

1. VirtualBox Image created
1. VirtualBox First time setup completed

### Machine State

1. `git` must be installed
1. web server must be installed

### Project Artifacts

The artifacts are already built, they just need to be installed onto the machine with `git`.

1. use `git` to clone build artifacts

### Web Server Configuration

`caddy` or `nginx` must be configured to catch HTTP requests and respond as a `file_server`, and then must be reloaded.

At this point the `Spring` project should be accessible in your browser.

{{% notice note %}}
This Spring project has a couple of different requirements than the React project. You will need to install the required version of java in order to run this project to set up a reverse proxy. The version you will need is `11`. In order to start the project you need to run the command `java -jar path/to/jar-file`
{{% /notice %}}

## Full Script Solution
{{% expand "Click Here for Solution" %}}

```bash
# Install Dependencies

## Update Package Repositories
sudo apt update -y

## Install Git
sudo apt install git

## Install openjdk-11-jre

sudo apt install -y openjdk-11-jre

## Install Caddy

sudo apt install -y curl

curl -1sLf \
  'https://dl.cloudsmith.io/public/caddy/stable/cfg/setup/bash.deb.sh' \
  | sudo bash

sudo apt update -y
sudo apt install caddy

## Clone Build Artifacts

git clone https://github.com/LaunchCodeTechnicalTraining/spring-todo-mvc-artifact

## Run the project jar file with jre in detached mode

java -jar /home/student/spring-todo-mvc-artifact/todo-api.jar &

## Configure Web Server

(
cat <<'EOF'
http://localhost {
        reverse_proxy http://localhost:8080
}
EOF
) > Caddyfile

sudo mv Caddyfile /etc/caddy/Caddyfile

sudo systemctl stop caddy

sudo caddy start

sudo caddy reload --config /etc/caddy/Caddyfile
```
{{% /expand %}}

### Check Browser

![Spring-Project-Browser-Validation](pictures/spring-validation.png?classes=border)