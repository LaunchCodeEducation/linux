---
title: "Bonus: Build Artifacts"
weight: 115
date: 2022-05-05
---

## React Initialization Script that Builds Artifacts

Below you will find a working solution to a script that builds the required artifacts for the `react-tic-tac-toe` project. 

In the previous sections we provided the build artifacts required to run the project. In the section below we build them within the script.

{{% expand "Click Here for Script" %}}
```bash
# Install Dependencies for React project

## Update Package Repositories

sudo apt update -y

wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

## Install Git

sudo apt install git

## Install Caddy

sudo apt install -y curl

sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https

curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update -y
sudo apt install caddy

## Install nvm

export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

## install node and npm version 16.3.0 (version the project uses)

nvm install 16.3.0
nvm use 16.3.0

## Cloning Repository to Local Machine

git clone https://github.com/LaunchCodeTechnicalTraining/react-tic-tac-toe-tutorial.git /home/student/Desktop/react-tic-tac-toe-tutorial

### Load project dependencies inside of directory

cd /home/student/Desktop/react-tic-tac-toe-tutorial

npm i

## Build dependences / Artifcats

npm run build

## Move artifacts: Create a /website at root of server

sudo mkdir /website

mv /home/student/Desktop/react-tic-tac-toe-tutorial/build /website

## Create a Caddyfile inside of /website  and caddy reload

(
cat <<'EOF'
https://localhost {
        root * /website/build
        file_server
}
EOF
) > /website/Caddyfile

caddy reload --config /website/Caddyfile
```
{{% /expand %}}