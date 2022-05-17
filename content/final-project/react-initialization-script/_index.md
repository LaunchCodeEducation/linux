---
title: "React Initialization Script"
weight: 105
date: 2022-05-05
---

## Get Organized

What needs to happen for the React project to be deployed?

### VirtualBox

1. VirtualBox Image created
1. VirtualBox First time setup completed

### Machine State

1. `git` must be installed
1. web server must be installed

### Project Artifacts

The artifacts are already built, they just need to be installed onto the machine with `git`.

1. use `git` to clone build artifacts

{{% notice note %}}
Build artifacts for this script: `https://github.com/LaunchCodeTechnicalTraining/react-tic-tac-toe-build-artifacts`
{{% /notice %}}

### Web Server Configuration

`caddy` or `nginx` must be configured to catch HTTP requests and respond as a `file_server`, and then must be reloaded.

At this point the `react` project should be accessible in your browser.

## Full Script Solution
{{% expand "Click Here for Solution" %}}
```bash
#!/bin/bash

# Install Dependencies

## Update Package Repositories
sudo apt update -y

## Install Git
sudo apt install git

## Install Caddy

### Install Curl (Needed to install Caddy)
sudo apt install -y curl

curl -1sLf \
  'https://dl.cloudsmith.io/public/caddy/stable/cfg/setup/bash.deb.sh' \
  | sudo bash

sudo apt update -y
sudo apt install caddy

## Cloning Build Artifacts

git clone https://github.com/LaunchCodeTechnicalTraining/react-tic-tac-toe-build-artifacts

## Configure Web Server

(
cat <<'EOF'
https://localhost {
        root * /home/student/react-tic-tac-toe-build-artifacts/
        file_server
}
EOF
) > Caddyfile

sudo mv Caddyfile /etc/caddy/Caddyfile

sudo systemctl stop caddy

sudo caddy start

## Reload Caddy
sudo caddy reload --config /etc/caddy/Caddyfile
```
{{% /expand %}}

### Check Browser