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

<!-- TODO: Script to solve a live coding problem -->

## Examples

Create a new file called `create-dir-file.sh`

```bash
## navgiate to /home/student/Desktop
cd /home/john/Desktop

## create new directory inside of /home/student/Desktop
mkdir new-directory

## navigate to  new-directory inside of /Desktop
cd new-directory

## create new file inside of new-directory
touch new-file
```

Add the above code to the file:

Run the command `bash create-dir-file.sh`

Create a new file called `high-low.sh`

```bash
#!/bin/bash

high_low=(15 10 -3 5 23 -5)

for item in ${high_low[@]}
do
	if [[ $item -gt $high_value ]]
	then
		high_value=$item
	fi
	if [[ $item -lt $low_value ]]
	then
		low_value=$item
	fi
done

echo "The highest value is: "$high_value
echo "The lowest value is: "$low_value
```

Add the above code to the file:

Run the command `bash high-low.sh`

<!-- - File with shebang:
  - `#!/bin/bash`
  - `echo "Hello World`
    - `./filename` -->
