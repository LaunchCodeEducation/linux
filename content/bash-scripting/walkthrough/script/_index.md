---
title: "Scripting"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 100
---

## Bash Scripting

A bash shell script is a file that holds a set of bash commands to be read and executed by `Bash`.

Bash files are commonly denoted with a `.sh` file extension for example: `example-script.sh`.

Additionally the first line of a Bash script commonly contains a **shebang**. A shebang is a line that informs the operating system of the exact shell to use when executing the script. The shebang simply points to the absolute path of the shell for example: `#!/bin/bash`.

{{% notice note %}}
Any valid bash syntax can be run in a file without the `.sh` extension and without a shebang when the `bash` command is invoked. However, to run a file without explicitly invoking the bash command, the bash script file requires a shebang and must be executable. 

Once these conditions are met the script can be invoked directly without the `bash` command. An example of this will be shown later in this chapter.
{{% /notice %}}

## Examples

The following examples are complete `bash` scripts that can be executed on any machine with the `bash` package.

### Create new directory/new file script

The first example:

1. navigates to a specific directory
1. creates a new directory
1. changes into the new directory
1. creates a new file

Create a new file called `create-dir-file.sh` and add the following contents:

```bash
#!/bin/bash

## navgiate to /home/student/Desktop
cd /home/student/Desktop

## create new directory inside of /home/student/Desktop
mkdir new-directory

## navigate to  new-directory inside of /Desktop
cd new-directory

## create new file inside of new-directory
touch new-file
```

Execute the script by invoking the `bash` package and providing the path to the newly created script as the argument:

```bash
bash create-dir-file.sh
```

Upon creating and executing the `create-dir-file.sh` script a new directory and file will be created in one fell swoop!

Look at the contents of the `/home/student/Desktop` and `/home/student/Desktop/new-directory` directories.

### LaunchCode Employee Script

The first script was pretty basic. Let's create a more complex script that combines multiple of the tools we've learned in this class. Let's scrape, extract, and transform some data into a more usable state.

The LaunchCode website provides an about page, and on the page is a listing of all current LaunchCode employees.

It looks similar to the following image:

![LC about page output](pictures/lc-about.png?classes=border)

Say we want a script that will: 
1. make a request for the raw `HTML`
1. extract the data we want with `grep`
1. trim the data using `sed`
1. write the output to a new file

{{% notice note %}}
The about page of the LaunchCode website is subject to change. To ensure the provided script will work we have provided the raw `HTML` as a part of this curriculum.
{{% /notice %}}

**The file the script will be requesting is found at the link of the following attachment.**

{{%attachments style="blue" title="Practice File" /%}}

By hovering over the file you can find the URL of this specific resource, in the bottom left corner of your web browser.

{{% notice note %}}
You can add that specific resource to the wget command inside of the following script! As I was creating this walkthrough the specific link for me was `http://localhost:1313.app/bash-scripting/walkthrough/script/_index.files/about.html`
{{% /notice %}}

 Create a new file called `lc-employee.sh` and add the following code:

```bash
cd /home/student/Desktop

mkdir launchcode-roster

cd launchcode-roster

wget http://lctt-linux.netlify.app/bash-scripting/walkthrough/script/_index.files/about.html

cat about | grep '<p style="line-height: 1.4;"><strong>.*</strong><br/>.*<br/>' | sed 's/^.*<strong>//g' | sed 's/<\/strong><br\/>/: /g' | sed 's/<br\/>.*$//g' > lc-employees.txt

cat lc-employees.txt | grep "^John\|Paul" > john-paul.txt
```

{{% notice warning %}}
The url you provide for the wget command must be correct in order for this to work properly! Make sure you copy the correct url from the `about.html` file! The `lctt-linux.netlify.app` portion of the URL has likely changed!
{{% /notice %}}

Execute the newly created script: 

```bash
bash lc-employee.sh
```

Output:

![bash lc-employee.sh output](pictures/bash-lc-employee.png?classes=border)

### Script Validation

Check to see if the script worked!

![validation](pictures/validation.png?classes=border)

- Navigate to your `Desktop` folder to view the newly created `launchcode-roster` directory.
- `cd` into the `launchcode-roster` directory and list the contents.
- `cat` out of the contents of the `john-paul.txt`

{{% notice green "Bonus" "rocket" %}}
 Check the contents of the `lc-employees.txt` file! Inside should be all of the employees of LaunchCode with their titles.
{{% /notice %}}


## Recap:
- Bash scripting description
  - `#!/bin/bash`: shebang
- Example Bash Scripts:
  - Script to change directories, create a new directory, add a file to new directory
  - Script to create a list of LaunchCode Employees and also separate John and Paul from the list!