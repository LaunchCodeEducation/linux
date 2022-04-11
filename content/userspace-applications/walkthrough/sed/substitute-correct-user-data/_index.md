---
title: "Substitute: Correct user-data.csv"
date: 2021-04-06
draft: false
weight: 100
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## Correct `user-data.csv`

The `user-data.csv` file we downloaded from `https://launchcodetecnicaltraining.org/api/walkthrough/user?data_format=csv` has a couple of mistakes we need to fix across the entire file.

1. Typo: company `mastercard` should be `Mastercard`
1. Typo: company `spectrum` should be `Spectrum`
1. Company `Stephens-Griffin` name changed to: `Stephens-Griffin-Ferguson`

## `sed` substitute 'mastercard' with 'Mastercard'

Run a substitute command:

```bash
sed 's/mastercard/Mastercard/' user-data.csv
```

Output:

![sed 's/mastercard/Mastercard/' user-data.csv output](pictures/sed-s-m-M.png?classes=border)

However, this doesn't alter the file it simply displays the substitution in STDOUT.

{{% notice green "Bonus" "rocket" %}}
You can see that the change didn't take place by running `grep 'mastercard' user-data.csv`:

![grep 'mastercard' user-data.csv output](pictures/grep-mastercard.png?classes=border)
{{% /notice %}}

### Write Changes

Write the changes to a new file named `user-data.corrected.csv`. This way the original file stays unchanged.

```bash
sed 's/mastercard/Mastercard/' user-data.csv > user-data.corrected.csv
```

### Validation

Since the substitution is writing to a file instead of routing to STDOUT the change is not seen automatically. There are many tools that allow you to view the file so the changes can be validated:

```bash
grep 'Mastercard' user-data.corrected.csv
```

Output:

![grep 'Mastercard' user-data.corrected.csv](pictures/grep-mastercard-corrected.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
Since you have access to both the original file and corrected file you could use `git diff` to view the differences between the two files:

```bash
git diff user-data.csv user-data.corrected.csv
```

Output:

![git diff user-data.csv user-data.corrected.csv output](pictures/git-diff.png?classes=border)

You can see the exact lines that were deleted and the lines they were replaced with. This is a `less` screen you can navigate with the arrow keys, `j` (up) and `k` (down) keys and type `q` to exit. 
{{% /notice %}}

## `sed` substitute 'spectrum' with 'Spectrum'

The file needs more corrections.

Run a substitute command & write:

```bash
sed -i 's/spectrum/Spectrum/' user-data.corrected.csv
```

### Validation

```bash
grep 'spectrum' user-data.corrected.csv
```

We should not see any records as the instances of `spectrum` were replaced by `Spectrum`

{{% notice green "Bonus" "rocket" %}}
We leave it up to you to run `grep 'Spectrum' user-data.corrected.csv` or `git diff user-data.csv user-data.corrected.csv` to further confirm the changes.
{{% /notice %}}

## `sed` substitute 'Stephens-Griffin' with 'Stephens-Griffin-Ferguson'

Run a substitute command & write:

```bash
sed -i 's/Stephens-Griffin/Stephens-Griffin-Ferguson/' user-data.corrected.csv
```

### Validation

```bash
grep 'Stephens-Griffin-Ferguson' user-data.corrected.csv
```

Output:

![grep 'Stephens-Griffin-Ferguson' user-data.corrected.csv output](pictures/grep-stephens-griffin-ferguson.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
You can run any `sed` scripts and edit the file in place by using the `-i` flag. This way you wouldn't need to read a file and then write out the same file.

Instead of:

```bash
sed 's/Stephens-Griffin/Stephens-Griffin-Ferguson/' user-data.corrected.csv > user-data.corrected.csv
```

This works:

```bash
sed -i 's/Stephens-Griffin/Stephens-Griffin-Ferguson/' user-data.corrected.csv
```
{{% /notice %}}
