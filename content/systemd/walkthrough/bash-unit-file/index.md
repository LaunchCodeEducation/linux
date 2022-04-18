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

This bash script can be converted into a `systemd` service by creating a valid unit file. After creating the unit file the service will be controllable with the `systemctl` tool.

Create a file in `/etc/systemd/system/` called `bash-garbage-collector.service` as the `root` user:

```bash
sudo touch /etc/systemd/system/bash-garbage-collector.service
```

Add the following contents to the file using your editor of choice (make sure you are still acting as the `root` user):

```bash
[Unit]
Description=An awesome bash garbage collector (files in a certain directory)

[Service]
ExecStart=/usr/bin/bash /home/student/bash-garbage-collector/empty.sh
Restart=never

[Install]
WantedBy=multi-user.target
```

Breakdown:

- **Description**: the human readable description of the service
- **ExecStart**: The command invoked when the service is started (in this case `/usr/bin/bash` is being used to execute `/home/student/bash-garbage-collector/empty.sh`)
- **Restart**: Instructions on how and when the service should restart (in this case never).
- **WantedBy**: The system level in which the service should be initialized if `enabled` (in this case just before the user login screen appears (a multi-user environment has been reached))

## Service Control via `systemctl`

### Start

```bash
sudo systemctl start bash-garbage-collector
```

After starting the service add contents to `/home/student/bash-garbage-collector/trash` wait 30 seconds and see how the directory and the `garbage.log` are affected.

### Stop

```bash
sudo systemctl stop bash-garbage-collector
```

After stopping the service the garbage collector is no longer running.

### Enable

```bash
sudo systemctl enable bash-garbage-collector
```

After enabling the service the garbage collector should start when the machine reboots.

{{% notice note %}}
You can reboot your virtual machine in many ways. The easiest is with the `reboot` command. After rebooting check the status of the service, and look over the contents of the `bash-garbage-collector/` directory.
{{% /notice %}}

### Disable

```bash
sudo systemctl disable bash-garbage-collector
```

After disabling the service it will no longer start when the computer starts.

## Service Failure

Right now the service file instructs `systemd` to **never** restart the running service. Even if the service fails and stops running `systemd` will leave it in a stopped state.

This can be tested by starting, and finding the `PID` of the service:

```bash
systemctl status bash-garbage-collector
```

Output:

```bash
Main PID: 556 (bash)
```

### Simulate Failure with `kill`

{{% notice warning %}}
The `PID` (process id) will be a different number on your virtual machine. When entering the next command make sure to use the `PID` of your specific service file!
{{% /notice %}}

We can simulate a failure by sending a `SIGKILL` signal with the `kill` command:

```bash
sudo kill -9 [YOUR-SERVICE-PID]
```

### Check Status

After simulating a catrastophic failure check the status of the service:

```bash
systemctl status bash-garbage-collector
```

### Configure Service to Restart on Failure

`systemd` can be told to **restart** a service when it fails. Change the `Restart` section of the `/etc/systemd/system/bash-garbage-collector.service` file to:

```bash
Restart=on-failure
```

Now `systemd` knows to restart the service when it has experienced a failure.

### Stop and Start Service

After making a change to a unit file you will need to stop and start the service again.

{{% notice note %}}
In some instances, depending on the state of the service when a change was made to the service's underlying unit file, the `systemd` tool may need to be restarted. If this is required your terminal will let you know, and will ask you to execute a command similar to:
```bash
sudo systemctl daemon-reload
```
If you see this, make sure to do it so that the change to the underlying unit file is loaded into `systemd` properly.
{{% /notice %}}

### Kill again

Find the `PID` of the service again and kill it with a `SIGKILL` signal (`-9`).

Check the status of the service. Take note of the new `PID` the service was assigned when it was restarted.