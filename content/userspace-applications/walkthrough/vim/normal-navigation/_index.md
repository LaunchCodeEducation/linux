---
title: "Normal Mode: File Navigation"
date: 2022-04-07
draft: false
weight: 125
---

## Normal Mode: File Navigation

One of `vim`'s major ideals is that the user's hands never need to leave the keyboard. Meaning various keys and keystrokes have been programmed to give the user navigation controls.

Most navigation occurs in `Normal` mode.

{{% notice warning %}}
This article will use the `user-data.csv` used in the previous `grep` and `sed` sections. If you do not already have the file, you can re-download it with:

```bash
curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv > user-data.csv
```

After running the command you should have a new copy of the `user-data.csv` file:

![validation image of the curl command](pictures/curl-user-data.png?classes=border)

The file should have 25001 lines in it (run `wc -l user-data.csv`):

![wc -l user-data.csv output](pictures/csv-validation.png?classes=border)

{{% /notice %}}

## Open `user-data.csv` with `vim`

First open the file:

```bash
vim user-data.csv
```

Output:

![vim user-data.csv output](pictures/vim-open-user-data-csv.png?classes=border)

By default, `vim` opens the file in `Normal` mode.

## Basic Navigation

### Navigate Down `j`

In `Normal` Mode the `j` key will move the cursor down one line.

Upon pressing the `j` key exactly one time it will move the cursor from over the `f` in `first_name` to the `A` in `Amy` immediately below it.

Try it out:

![vim normal mode j press output](pictures/vim-j-one.png?classes=border)

Notice the cursor moved over the `A` in `Amy`.

What happens if the `j` key is pressed five more times? It should be over the `W` in `Wesley`:

![vim normal mode j press five more times output](pictures/vim-j-five.png?classes=border)

### Navigate Up `k`

In `Normal` mode the `k` key will move the cursor up one line.

As the cursor is currently over the `W` in `Wesley` pressing `k` one time should place the cursor over the `B` in `Brian`:

![vim normal mode k press output](pictures/vim-k-one.png?classes=border)

### Navigate Right `l`

In `Normal` mode the `l` key will move the cursor right one character.

The cursor is currently over the `B` in `Brian` pressing `l` one time should place the cursor over the `r` in `Brian`:

![vim normal mode l press output](pictures/vim-l-one.png?classes=border)

### Navigate Left `h`

In `Normal` mode the `h` key will move the cursor left one character.

The cursor is currently over the `r` in `Brian` pressing the `h` key one time should place the cursor over the `B` in `Brian`:

![vim normal mode h press output](pictures/vim-k-one.png?classes=border)

## Advanced Navigation

The `Normal` mode basic navigation keys (`h`, `j`, `k`, `l`) are analogous to the direction keys in `Insert` mode. Both suffer from the same drawback: tedious and slow navigation. Using the mouse would be a better experience than trying to navigate through a 25001 line file with the basic navigation commands.

Luckily, `vim` has a ton of advanced Navigation commands in `Normal` mode we will explore:

- go to specific line
- go to next word
- go to previous word
- go to beginning of line
- go to end of line
- go to top of file
- go to bottom of file

## Go to specific line `:[line-number]` + `<enter>`

The cursor is currently on `B` in `Brian` typing`:66` **and hitting enter** will navigate to the 66th line of the file:

![vim normal mode :66 enter output](pictures/vim-colon-66.png?classes=border)

This command took us to the first character of the 66th line `E` in `Ernest`.

Let's navigate back to line 6 typing `:6` **and hitting enter**:

![vim normal mode :6 enter output](pictures/vim-k-one.png?classes=border)

{{% notice note %}}
Two things to take notice of:

- giving a goto line is a `Normal` mode command requiring an enter key press
- the bottom right corner of the `vim` terminal window displays two numbers (like `6,1`) representing the cursor location

The following picture will highlight the cursor location:

![vim normal mode cursor location highlighted](pictures/vim-cursor-loc-highlighted.png?classes=border)
{{% /notice %}}

## Navigate Next Word `w`

In `Normal` mode the `w` key will move the cursor forward one word.

The cursor is currently on `B` in `Brian` (line 6) pressing `w` one time will place the character on the next word (in this case the comma):

![vim normal mode w press output](pictures/vim-w-one.png?classes=border)

Pressing `w` three more times should move the cursor to the `i` in `iperez@example.net`:

![vim normal mode w three more presses output](pictures/vim-w-three.png?classes=border)

## Navigate Previous Word `b`

In `Normal` mode the `b` key will move the cursor back one word.

The cursor is currently on the `i` in `iperez@example.net` pressing the `b` should move the cursor back to the `,` preceding the word:

![vim normal mode b press output](pictures/vim-b-one.png?classes=border)

## Navigate to Beginning of Current Line `0`

In `Normal` mode the `0` (zero) key will move the cursor to the beginning of the current line.

The cursor is currently located at `6,14` pressing the `0` key will move the cursor to `6,1`:

![vim normal mode 0 press output](pictures/vim-k-one.png?classes=border)

## Navigate to End of Current Line `$`

In `Normal` mode the `$` (`shift` + `4`) key combo will move the cursor to the end of the current line.

The cursor is currently located at `6,1` pressing the `$` key combination will move the cursor to `6,45`:

![vim normal mode $ press output](pictures/vim-$.png?classes=border)

## Navigate to Top of File `gg`

In `Normal` mode the `gg` key combo will move the cursor to the top of the file.

The cursor is currently located at `6,45` pressing the `gg` key combo will move the cursor to `1,1`:

![vim normal mode gg press output](pictures/vim-gg.png?classes=border)

## Navigate to Bottom of File `G`

In `Normal` mode the `G` (`shift` + `g`) key combo will move the cursor to the bottom of the file.

The cursor is currently located at `1,1` pressing the `G` key combo will move the cursor to `25001,1`:

![vim normal mode G press output](pictures/vim-G.png?classes=border)

## Recap

Navigating in `vim` can be accomplished in either `Normal` or `Insert` modes with basic navigation commands.

However, `vim` `Normal` mode provides many additional commands for navigating the file in an efficient manner.

{{% notice note %}}
There are additional navigation commands in `vim`, but you will have to research those on your own!
{{% /notice %}}

{{% notice green "Bonus" "rocket" %}}
You can provide a numeric prefix to the majority of the navigation commands like `5` and it will perform the provided navigation action the provided number of times.

For example:

- Navigate down five lines with `5j`
- Navigate up 15 lines with `15k`
- Navigate 32 characters to the right with `32l`
- Navigate 6 characters to the left with `6h`
- Navigate forward 3 words with `3w`
{{% /notice %}}