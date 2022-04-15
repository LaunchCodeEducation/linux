---
title: "Chaining Sed"
date: 2021-04-06
draft: false
weight: 125
---

## Chaining Sed

Another benefit of using `STDIN` when working with `sed` is the ability to chain multiple substitutions (or other `sed` scripts). The final example of the last article was an example of chaining `sed`, but you will get another example here.

In an earlier walkthrough you corrected the `user-data.csv`.

It took a total of three steps to complete the task. However, you could have chained all of the steps together using the pipe (`|`) operator.

Let's give it a try:

```bash
sed 's/mastercard/Mastercard/' user-data.csv | sed 's/spectrum/Spectrum/' | sed 's/Stephens-Griffin/Stephens-Griffin-Ferguson/' > user-data.corrected2.csv
```

### Validation

```bash
cat user-data.corrected2.csv
```

There shouldn't be any `spectrum` matches:

```bash
grep 'spectrum' user-data.corrected2.csv
```

There shouldn't be any `mastercard` matches:

```bash
grep 'mastercard' user-data.corrected2.csv
```

There should only be one `Stephens-Griffin-Ferguson` match:

```bash
grep 'Stephens-Griffin-Ferguson' user-data.corrected2.csv
```

We did not provide the pictures as evidence, because you should have the skills now to validate these changes yourself.