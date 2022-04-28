---
title: "Exercises"
date: 2022-03-02T09:54:08-06:00
draft: false
weight: 115
---

## Exercises

{{% children %}}

## Questions & Answers

### What is the purpose of `systemd`?

### What is `systemctl`?

### What is a unit file?

### What are the five primary commands of `systemctl` introduced in this class?

{{% expand "CLICK FOR ANSWER" %}}
1. `status`
1. `start`
1. `stop`
1. `disable`
1. `enable`
{{% /expand %}}

## Which of the five commands is necessary to view information about a given unit?

{{% expand "CLICK FOR ANSWER" %}}
`status`
{{% /expand %}}

### Which of the five commands are necessary for managing a units state?

{{% expand "CLICK FOR ANSWER" %}}
- `start`
- `stop`
{{% /expand %}}

### Which of the five commands are necessary for controlling when a unit starts at a specific computer target?

{{% expand "CLICK FOR ANSWER" %}}
- `enable`
- `disable`
{{% /expand %}}

### What must be included in a unit file to start a service?

{{% expand "CLICK FOR ANSWER" %}}
```systemd
[Service]
ExecStart=valid command to start the service
```
{{% /expand %}}

### What must be included in a unit file to configure a unit to restart on failure?

{{% expand "CLICK FOR ANSWER" %}}
```systemd
[Service]
Restart=on-failure
```
{{% /expand %}}

### What must be included in a unit file to configure a unit to start at a specific computer target (like on boot)?

{{% expand "CLICK FOR ANSWER" %}}
```systemd
[Install]
WantedBy=some-defined.target
```
{{% /expand %}}