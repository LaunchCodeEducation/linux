---
title: "Create File"
date: 2022-04-07
draft: false
weight: 100
---

## Creating File

Executing `vim [file-name]` from the terminal will either create a new file or will open the file, if it currently exists.

From the home directory enter:

```bash
vim temp-file.txt
```

Upon executing the command a new file named `temp-file.txt` will be created and the `vim` text editor will be opened taking over your entire terminal.

![vim temp-file.txt output](pictures/vim-temp-file.png?classes=border)

Note the file is empty, which makes sense as the file was just created. The file name is listed at the bottom of the terminal window: `"temp-file.txt" [New File]`. This is standard behavior for creating a new file using `vim`.

When a file is opened `vim` will be in `Normal` mode by default.

The next article will show how to write and quit the file.