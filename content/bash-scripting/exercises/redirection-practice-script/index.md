---
title: "Redirection Practice Script"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 100
---

## Requirements:

Create a script that does the following:
- Creates a new directory called `redirect-practice` inside of your `home` directory
- Creates a file called `redirection-name` inside of the `redirect-practice` directory
- Creates a file called `redirection-files` inside of the `redirect-practice` directory
- Creates a file called `redirection-directories` inside of the `redirect-practice` directory
- Appends your name to the `redirection-name` file
- Appends the list of files inside of your `home` directory to the `redirection-files` file
- Appends only a list of directories inside of the `redirection-directories` file. 


{{% expand "Click Here for Answer" %}}
```bash
mkdir ~/redirect-practice

path_to_dir=~/redirect-practice

touch $path_to_dir/redirection-name

touch $path_to_dir/redirection-files

touch $path_to_dir/redirection-directories

echo "[Your Name]" > $path_to_dir/redirection-name

ls ~/ > $path_to_dir/redirection-files

ls -l ~/ | grep "^d" > $path_to_dir/redirection-directories
```
{{% /expand %}}