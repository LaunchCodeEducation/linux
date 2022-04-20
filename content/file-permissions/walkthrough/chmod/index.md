---
title: "Changing File Permissions"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 105
---

## Name

> `chmod` command - change permissions of file or directory

## Usage

The chmod command allows you to change the permissions on any given file so that you can update the `read`, `write`, and `execute` status.

```bash
chmod [OPTIONS] file-name
```

## Chmod Numerical Expressions

When changing permissions of a file with the `chmod` command it would help to understand the numerical expressions for each type.
- `Read` (r) is represented by the number `4`.
- `Write` (w) is represented by the number `2`.
- `Execute` (x) is represented by the number `1`.

| Chmod | Description |
| :---: | :--- |
| 7 | 4(r) + 2(w) + 1(x) = 7 `rwx`: read, write and execute |
| 6 | 4(r) + 2(w) = 6 `rw` -: read and write |
| 5 | 4(r) + 1(x) = 5 `r-x`: read and execute |
| 4 | 4(r) `r` - -: read only |
| 3 | 2(w) + 1(x) = 3 `-wx`: write and execute |
| 2 | 2(w) `-w-`: write only|
| 1 | 1(x) `- -x`: execute only |
| 0 | 0 `- - -` : none |


## Example

chmod - change file mode bits

<!-- bit notatation:

- 7 `4(r) + 2(w) + 1(x)` rwx: read, write and execute
- 6 `4(r) + 2(w)` 	rw-: read and write
- 5 `4(r) + 1(x)` r-x:	read and execute
- 4 `4(r)` r--: read only
- 3 `2(w) + 1(x)` 	-wx: write and execute
- 2 `2(w)` 	-w-: write only
- 1 `1(x)` 	--x: execute only
- 0 `0` ---: none 


numerical file permissions --> -->
