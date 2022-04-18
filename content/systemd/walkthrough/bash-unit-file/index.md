---
title: "Bash Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 115
---

## Setup

### Clone

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/bash-garbage-collector
```

### Review Source Code

```bash
ls bash-garbage-collector
```

```bash
cat empty.sh
```

```bash
#!/bin/bash

dir=/home/student/bash-garbage-collector/trash
log=/home/student/bash-garbage-collector/garbage.log

while true
do
    if [[ $(ls $dir) == "" ]]
    then
        echo "$(date): no contents detected in $dir" >> $log
    else
        echo "$(date): contents detected in $dir...emptying" >> $log
        rm $dir/*
    fi
    sleep 30
done
```

A simple script that checks the contents of `/home/student/bash-garbage-collector/trash` every 30 seconds. If contents exist at the location it logs that contents were detected and deletes the contents. If contents were not detected it simply logs that no contents were found.

### Run Script

From the project directory run:

```bash
bash empty.sh
```

Feel free to add files to `/home/student/bash-garbage-collector/trash` after 30 seconds check the contents of `/home/student/bash-garbage-collector/garbage.log` and the `trash/` directory to see how the effects of the script.

### Stop Script

The script can be stopped by entering `ctrl` + `c` to send the interrupt signal to the running process.

## Create Unit File

Create a unit file for this script. This way it can be managed and controlled with `systemctl` as a `systemd` unit.

The file should be called `/etc/systemd/system/bash-garbage-collector.service`:

```bash
[Unit]
Description=An awesome bash garbage collector (files in a certain directory)

[Service]
ExecStart=/usr/bin/bash /home/student/bash-garbage-collector/empty.sh
Restart=never

[Install]
WantedBy=multi-user.target
```

## Service Control via `systemctl`

### Start

```bash
sudo systemctl start bash-garbage-collector
```

### Stop

```bash
sudo systemctl stop bash-garbage-collector
```

### Enable

```bash
sudo systemctl enable bash-garbage-collector
```

### Disable

```bash
sudo systemctl disable bash-garbage-collector
```

## Service Failure

### Simulate Failure with `kill`

### Check Status

### Configure Service to Restart on Failure

### Restart `systemd`

### Start service

### Kill again

### Still rolling