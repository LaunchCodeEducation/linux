---
title: "Demo"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 3
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Demo: Creating & Executing a Bash Script

- `mkdir /home/student/bin`
- `nano /home/student/bin/whattimeisit`

```bash
#!/bin/bash

echo "Hello Paul..."
echo "It is currently $(date)"
echo "Have a nice day!"
```

- run the file `bash /home/student/bin/whattimeisit`
- make the file executable `chmod +x /home/student/bin/whattimeisit`
- run the file `/home/student/bin/whattimeisit`
  - or `./bin/whattimeisit`
  - or `bash /home/student/bin/whattimeisit`

### Adding to Path

- what is my $PATH `echo $PATH`
- I just want to add this new dir to my path `PATH=$PATH:/home/student/bin`
- now I can just run `whattimeisit`
- what if I want to change the name of my program?
  - `rename whattimeisit when`
- run `when`
- what happens if we `which when`
- what happens if we `man when`

### Symlink

- pythonc omes standard as apart of most Linux distros
- `which python` --> so where is it?
- `which python3` --> here it is (python 2 is dead and has been fully replaced by python3) --> older versions of Ubuntu did have python which defaulted to Python2 & also had a version of Python3 installed.
- let's take a look at /usr/bin `ls /usr/bin`
  - python should be here, manually search for it
    - why is it blue?
    - why is there a Python3.8 that is green?
- `ls -l /usr/bin | grep python3`
- what is a Symlink?

### Change name back and create a symlink pointing to it name when

- `rename when whattimeisit`
- `ln -s whattimeisit when`
- how can we run this program?
  - `whattimeisit`
  - `when`

  This explains what Python3 is in /usr/bin -- just a symlink pointing at the actual python3.8 interpreter!