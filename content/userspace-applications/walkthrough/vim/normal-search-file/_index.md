---
title: "Normal Mode: Search File"
date: 2022-04-07
draft: false
weight: 130
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-07 # UPDATE ANY TIME CHANGES ARE MADE
---

## Normal Mode: Search File

Navigating a file is a crucial skill. The `Normal` mode of `vim` provides a search function that allows you to search for specific characters, words, phrases, or additional Regular Expressions.

To perform a search in `vim` `Normal` mode you simply need to press the forward slash (`/`) character and type in your search term. While typing `vim` will automatically take you to the first encountered search term from the cursors current location.

Once you are happy with your search term you can hit enter and all of the words matching your pattern will be highlighted.

## Search `/Paul`

In `Normal` mode, from the cursor position `1,1` (get there by pressing `gg`) press `/` and then type `Paul`:

![vim normal mode search Paul output](pictures/vim-search-paul.png?classes=border)

Before hitting enter `vim` automatically moved the cursor to the first matched instance. If more letters are typed they will be added to the search term. To signal the end of a `vim` `Normal` mode search the `enter` key must be pressed:

![vim normal mode search Paul + enter output](pictures/vim-search-paul-enter.png?classes=border)

After pressing `enter` the screen has changed in a subtle, but informative way:

- The cursor has been placed on the first match of the provided pattern
- The cursor location has been updated in the bottom right corner of the `vim` terminal window
- `/Paul` is still recorded as the in memory search pattern

Having the search term still recorded in `vim`s memory is very handy as it allows us to provide additional key presses to advance to the next, or previous match in the file.

## Navigate to Next Match in File `n`

After entering a search in `Normal` mode `vim` can be instructed to advance to the next matched result by pressing the `n` key:

![vim normal mode search n press](pictures/vim-n-one.png?classes=border)

The `n` key press placed the cursor on the next matched location `215,1`.

The `n` key can be pressed any number of times after a search has been entered.

## Navigate to Previous Match in File `N`

After entering a search in `Normal` mode `vim` can be instructed to backtrack to the previous matched result by pressing the `N` (`shift` + `n`) key combo:

![vim normal mode search N press](pictures/vim-N-one.png?classes=border)

After pressing `N` our cursor changed from location `215,1` to `156,1`.

The `N` key can be pressed any number of times after a search has been entered.

## Search `/^\(John\|Paul\)`

Within `vim` `Search` mode enter the following regular expression:

```bash
^\(John\|Paul\)
```

![vim search regex](pictures/vim-search-regex.png?classes=border)

A match for our pattern was found at cursor start `19,1`.

Hit `n` and `N` each a few times to see that both `John` and `Paul` at the beginning of the line are matching our regular expression.

Some matches found at cursor locations:

- `19,1`
- `24,1`
- `59,1`
- `156,1`
- `192,1`
- `209,1`
- `24517,1`
- `24832,1`

{{% notice note %}}
The regular expression `^(John|Paul)` needed to be escaped in a way that `vim` understands. The `(`, `)` and `|` characters need to be escaped in `vim` so it doesn't search for the string representation of those characters.

There is a general syntax for regular expressions, however the various tools and programming langauges that implement regular expressions may use the standard regular expression syntax in different ways. This requires escaping to work with regular expressions across tools.
{{% /notice %}}

{{% notice green "Bonus" "rocket" %}}
After performing a search both advance to next match (`n`) and backtrack to previous match (`N`) can be provided with a numeric prefix (like `5`) and the action will be performed the specific number of times.
{{% /notice %}}