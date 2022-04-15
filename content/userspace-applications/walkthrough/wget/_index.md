---
title: "wget"
date: 2021-03-22
draft: false
weight: 100
---

## Name

> Wget - The non-interactive network downloader.

## Purpose

Download files over a network.

You can use it to download files over private networks like your home, school, or work network.

You can use it to download files over public networks like the internet.

{{% notice note %}}
You will only be seeing examples of downloading files over the internet.
{{% /notice %}}

## Usage

```bash
wget [url]
```

Using `wget` you can download the file using its unique URL. The downloaded file can be any format.

Some examples:
- HTML File: `.html`
- Debian Package File: `.deb`
- Comma Separated Values: `.csv`
- Python: `.py`
- Shell: `.sh`
- Zipped Directory: `.zip`
- Archived Directory: `.tar.gz`
- Image: `.png`, `.jpeg`, `.jpg`
- etc...

### Example

Make a `wget` request for the file at `https://www.launchcode.org`:

```bash
wget https://www.launchcode.org
```

Results:

![wget launchcode.org](pictures/wget-launchcode.png?classes=border)

After making the `wget` request you can see a new file was downloaded and exists in the pictured user's home directory: `index.html`.

{{% notice green "Bonus" "rocket" %}}
You can explore the contents of the newly downloaded `index.html` with the `cat` command.
{{% /notice %}}

## Practice Files

For your convenience we have provided files for you to practice on directly with this curriculum.

{{% attachments style="blue" title="Practice Files" /%}}

By hovering over the files you can see the URL of the specific resource, in the bottom left corner of your web browser.

![hover for URL](pictures/hover-for-url.png?classes=border)

The url from the picture above is: `localhost:1313/userspace-applications/walkthrough/wget/_index.files/hello.py`

{{% notice warning %}}
The URL has the following format: `protocol://domain/path` to future proof this curriculum we will simply provide the `path` to each of the files, you will be responsible for providing the protocol & domain. So the example picture from above would be: `/userspace-applications/walkthrough/wget/_index.files/hello.py`, however you would need to add the protocol, and domain before executing the command.
{{% /notice %}}


## Download `hello.txt`

Craft a `wget` request to download the `hello.txt` file:

```bash
wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/hello.txt
```

Command output:

![wget hello.txt](pictures/wget-hello-txt.png?classes=border)

### Validation

Check the contents of the downloaded file with `cat`:

```bash
cat hello.txt
```

Command output:

![cat hello.txt](pictures/cat-hello-txt.png?classes=border)

## Download `hello.sh`

Craft a `wget` request to download the `hello.sh` file:

```bash
wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/hello.sh
```

Command output:

![wget hello.sh](pictures/wget-hello-sh.png?classes=border)

### Validation

Check the contents of the downloaded file with `cat`:

```bash
cat hello.sh
```

Command output:

![cat hello.sh](pictures/cat-hello-sh.png?classes=border)

This file happens to be a `bash` script that you can execute with the `bash` command:

```bash
bash hello.sh
```

Command output:

![bash hello.sh](pictures/bash-hello-sh.png?classes=border)

## Download `hello.py`

Craft a `wget` request to download the `hello.py` file:

```bash
wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/hello.py`
```

Command output:

![wget hello.py](pictures/wget-hello-py.png?classes=border)

### Validation

Check the contents of the downloaded file with `cat`:

```bash
cat hello.py
```

![cat hello.py](pictures/cat-hello-py.png?classes=border)

This file happens to be a `python` script that you can execute with the `python3` interpreter:

```bash
python3 hello.py
```

Command output:

![python3 hello.py](pictures/python-hello-py.png?classes=border)

## Download `roster.csv`

Craft a `wget` request to download the `roster.csv` file:

```bash
wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/roster.csv
```

Command output:

![wget roster.csv](pictures/wget-roster-csv.png?classes=border)

### Validation

Check the contents of the file with `cat`:

```bash
cat roster.csv
```

![cat roster.csv](pictures/cat-roster-csv.png?classes=border)

## Outside Example (Imgur)

Let's find the link for a grumpy cat photo: https://imgur.com/gallery/Xl0W2iX, open dev tools, find `src=` of the image which is: `https://i.imgur.com/Xl0W2iX.jpeg`.

Let's request that specific file with `wget`.

```bash
wget https://i.imgur.com/Xl0W2iX.jpeg
```

![wget imgur](pictures/wget-imgur.png?classes=border)

### Validation

`wget` downloaded a file named `Xl0W2iX.jpeg`, let's open it in Firefox and see the photo.

![browser rendered PNG](pictures/browser-rendered-png.png?classes=border)

{{% notice note %}}
To open a file in Firefox, first open the browser, then hit `ctrl` + `o` to open a new file, then select the file you just downloaded in your home directory: `Xl0W2iX.jpeg`.
{{% /notice %}}

## Recap

We can use the `wget` tool to download files from the internet.