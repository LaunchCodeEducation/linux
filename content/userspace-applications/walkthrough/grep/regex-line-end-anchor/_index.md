---
title: "Regex: Line End Anchor"
date: 2021-04-04
draft: false
weight: 105
---

## Regular Expression Line End Anchor: `$`

You can match the end of a line with the Regular Expression line end anchor `$`.

In the case of this specific data-set company names come at the end of each line.

### Match `'s$'`

Let's match all lines that end with the letter `s`:

```bash
grep 's$' user.csv
```

Output:

![grep 's$' output](pictures/grep-line-end-anchor.png?classes=border)

Any line that ends with the letter `s` has been matched, in the case of this dataset `Express Scripts` and `Edward Jones` both match our provided pattern.

### Match `'Accenture$'`

Since the last entry in each record is a company name let's match all records that have `Accenture` as the company:

```bash
grep 'Accenture$' user.csv
```

![grep 'Accenture$'](pictures/grep-line-end-anchor-two.png?classes=border)

Every line that ends with `Accenture` is a part of the output from this `grep` command.

{{% notice note %}}
This is another simple RegEx concept and syntax you can use to create better matching patterns.
{{% /notice %}}