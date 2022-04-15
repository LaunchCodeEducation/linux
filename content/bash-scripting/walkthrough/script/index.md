---
title: "Scripting"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 100
---

## Bash Scripting

- A bash shell script is a file that holds a set of bash commands to be read and executed by `Bash`.
  - bash files are commonly denoted with a `.sh`
    - `example-script.sh`
  - `#!/bin/bash`: shebang. Placed at the top of each bash script in order to let the file know what command to run. 

## Example

- File with following script:
  - `cd Desktop`
  - `mkdir example-directory`
  - `cd example-directory`
  - `touch example-file`

- File with shebang:
  - `#!/bin/bash`
  - `echo "Hello World`
    - `./filename`
