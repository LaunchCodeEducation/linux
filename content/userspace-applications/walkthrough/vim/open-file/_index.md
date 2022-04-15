---
title: "Open File"
date: 2022-04-07
draft: false
weight: 110
---

## Opening an Existing File

With `vim` an existing file can be opened by entering `vim [file-name]` in the `bash` shell.

Open the file created in the last article by entering: `vim temp-file.txt`

![vim temp-file.txt output](pictures/vim-temp-file.png?classes=border)

{{% notice note %}}
Opening a file looks very **similar** to creating a new file. The only difference in this image from the image in the original creation article is the text at the bottom of the file:

```bash
"temp-file.txt" 0L, 0C
```

After creating the file initially it was:

```bash
"temp-file.txt" [New File]
```

A subtle, but informative difference.
{{% /notice %}}