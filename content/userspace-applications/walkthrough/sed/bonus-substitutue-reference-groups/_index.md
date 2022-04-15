---
title: "Bonus: Substitute: Reference Match Groups"
date: 2021-04-06
draft: false
weight: 130
---

## BONUS

This entire section is a bonus. It probably won't be covered, but you can run the examples to see what is happening, and learn even more about RegEx and `sed`.

## Bonus: Reference Groups

### Enter a Nickname

```bash
sed -E 's/(Phillip),(Holmes),/\1 "Phil",\2,/' user-data.corrected.csv | grep 'Phillip "Phil"'
```

The replacement text is:

- `\1`: text from first match group
- ` "Phil",`: the exact string of one space, quotes around Phil and a comma
- `\2`: text from second match group
- `,`: an exact comma

### Switch first_name & last_name columns

```bash
sed -E 's/^([^,]+,)([^,]+,)/\2\1/' user-data.corrected.csv
```

The first_name and last_name columns were switched!

## Switch all the columns around

```bash
sed -E 's/^([^,]+),([^,]+),([^,]+),(.*)/\4,\2,\1,\3/' user-data.corrected.csv
```

Reorders all the records in the file to be:

1. Company
1. last_name
1. first_name
1. email

{{% notice note %}}
Outside of showing how matching groups can be referenced in `sed` the examples in this article use the `-E` option which informs `sed` to run as `esed` using the extended regular expression syntax. The extended regular expression syntax has different default behavior and changes what symbols need to be escaped. `egrep` is usually closer to actual RegEx defined syntax than regular `grep` is. However, they both work.
{{% /notice %}}