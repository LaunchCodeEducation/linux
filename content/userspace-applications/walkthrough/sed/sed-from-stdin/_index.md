---
title: "Sed From STDIN"
date: 2021-04-06
draft: false
weight: 120
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## `sed` from STDIN

So far we have only performed `sed` substitute commands using a file as input, however we can re-route STDOUT from another command to use as the STDIN for `sed`.

This allows us to combine `sed` with other tools like `grep`.

In this example we will be using `grep` to match users with a specific last name. However, we don't want the Company the person works for, just their first and last names, and their email address. So we will use `sed` to trim out the company of our filtered dataset.

## `grep` Last Name: `Johnson`

```bash
grep '^[^,]\+,Johnson' user-data.csv
```

Output:

![grep '^[^,]\+,Johnson' user-data.corrected.csv output](pictures/grep-johnson.png?classes=border)

This `grep` and regular expression combo matched all individuals with a first name, and the last name of Johnson.

{{% notice note %}}
This `grep` command is using two regular expression symbols we have not seen before:

- `[^,]`: exclusion group, match any character other than the characters found inside of the match group `[^]` in this case a comma `,`
- `+`: match at least one, but as many additional characters that fit the pattern

Altogether: `'^[^,]\+,Johnson'` is a regular expression for:

1. match the beginning of the line (`^`)
1. match any character except for characters found in the exclusion group, in this case just a comma (`,`)
1. match at least one of the preceding pattern (anything but comma), but as many characters as you can: `\+`
1. match exactly one comma (`,`)
1. match exactly `Johnson`

- `Sally,Johnson`: match
- `Fred,Johnson`: match
- `Sally,Kemper`: no match
- `,Johnson`: no match
- `Fred,,Johnson`: no match

{{% /notice %}}

## `sed` Substitute Company with Nothing

As of now our output contains all the people we want to email, but we currently have each person's employer, which we don't care about. Let's substitute and replace the company with no characters, effectively deleting the section.

```bash
grep '^[^,]\+,Johnson' user-data.corrected.csv | sed 's/[^,]\+//4'
```

Output:

![grep '^[^,]\+,Johnson' user-data.corrected.csv | sed 's/[^,]\+//4' Output](pictures/grep-sed-remove-company.png?classes=border)

That was pretty slick. Let's break down the `sed` substitution: `s/[^,]\+//4`.

- `s/regex/replacement-text/flag`
- `s`: substitute
- `/[^,]\+/`: regex saying match at least one charcter not in the exclusion group (comma), but match as many as possible
- `//`: empty replacement-text, after matching the pattern it should substituted with nothing
- `/4`: make the substitution on the 4th match in the line

{{% notice note %}}
You can visualize the four sections with `grep` and it will give you a better understanding of exactly what was replaced with nothing on each line:

```bash
grep '^[^,]\+,Johnson' user-data.corrected.csv | grep '[^,]\+'
```

Output:

![grep '^[^,]\+,Johnson' user-data.corrected.csv | grep '[^,]\+' output](pictures/grep-grep.png?classes=border)

Take note that each line has matched exactly four segments, but no actual commas. 

- the first name would be removed by providing a `1` flag
- the last name would be removed by providing a `2` flag
- the email would be removed by providing a `3` flag
- the company would be removed by providing the `4` flag
- all matches would be removed by providing the `g` flag (which would only leave the three commas).

{{% /notice %}}

## `sed` Substitute Hanging Command with Nothing

At this point in time we have our email list: all the `Johnsons`, their emails, but not their employer.

Each line has a hanging comma. The hanging comma can be matched and substituted with `sed`:

```bash
grep '^[^,]\+,Johnson' user-data.corrected.csv | sed 's/[^,]\+//4' | sed 's/,//3'
```

Output:

![grep '^[^,]\+,Johnson' user-data.corrected.csv | sed 's/[^,]\+//4' | sed 's/,//3' output](pictures/grep-sed-sed.png?classes=border)

Goodbye trailing comma!

## Writing the Stream

The matched lines (`grep`) and substitutions (`sed`) have transformed our `user-data.corrected.csv` in to a family email list for the `Johnsons`, but the end result has been displayed to `STDOUT`.

`STDOUT` can be redirected to a file by using the `bash` redirection operator (`>`) that results in a file with the matching, and substitutions:

```bash
grep '^[^,]\+,Johnson' user-data.corrected.csv | sed 's/[^,]\+//4' | sed 's/,//3' > johnson-email-list.csv
```

### Validation

Check the contents of the working directory:

```bash
ls
```

Output:

![ls output](pictures/ls.png?classes=border)

Check the contents of the file:

```bash
cat johnson-email-list.csv
```

![cat johnson-email-list.csv output](pictures/cat-johnson.png?classes=border)