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

Bash files are commonly denoted with a `.sh`
- `example-script.sh`
- `#!/bin/bash`: shebang. Placed at the top of each bash script in order to let the file know what command to run.

{{% notice note %}}
You can still run a script with the `bash` command on a file that does not hold the `#!/bin/bash` shebang. In order to run a file without the bash command it requires the file to be executable. Once a file is executable you can simply call the file with path-to-file/filename
{{% /notice %}}

## Examples

### Create new directory/new file script

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

### LaunchCode Employee Script

To ensure that you have the correct file for the following example it has been provided below:

{{%attachments style="blue" title="Practice File" /%}}

By hovering over the file you can find the URL of this specific resource, in the bottom left corner of your web browser.

{{% notice note %}}
You can add that specific resource to the wget command inside of the following script! As I was creating this walkthrough the specific link for me was `http://localhost:1313/bash-scripting/walkthrough/script/_index.files/about.html`
{{% /notice %}}

Create a new file called `lc-employee.sh`

```bash
cd /home/john/Desktop

mkdir launchcode-roster

cd launchcode-roster

wget http://localhost:1313/bash-scripting/walkthrough/script/_index.files/about.html

cat about | grep '<p style="line-height: 1.4;"><strong>.*</strong><br/>.*<br/>' | sed 's/^.*<strong>//g' | sed 's/<\/strong><br\/>/: /g' | sed 's/<br\/>.*$//g' > lc-employees.txt

cat lc-employees.txt | awk '{employees+=1}END{print "total employees: " employees}' >> lc-employees.txt

cat lc-employees.txt | grep "^John\|Paul" > john-paul.txt
```

Add the above code to the file:

Run the command `bash lc-employee-sh`


## Recap:
- Bash scripting description
  - `#!/bin/bash`: shebang
- Example Bash Scripts:
  - Script to change directories, create a new directory, add a file to new directory
  - Script to create a list of LaunchCode Employees and also separate John and Paul from the list!