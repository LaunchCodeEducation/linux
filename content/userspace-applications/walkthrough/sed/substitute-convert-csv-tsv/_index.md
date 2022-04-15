---
title: "Substitute: Convert CSV to TSV"
date: 2021-04-06
draft: false
weight: 110
---

## `sed` substitute ',' with '\t'

Convert the user-data.corrected.csv to a tsv file:

Run:

```bash
sed 's/,/\t/g' user-data.corrected.csv > user-data.corrected.tsv
```

### Validation

```bash
ls
```

Output:

![ls output](pictures/ls.png?classes=border)

A new file exists: `user-data.corrected.tsv`.

Inspect it:

```bash
cat user-data.corrected.tsv
```

Output:

![cat user-data.corrected.tsv output](pictures/cat-tsv.png?classes=border)