---
title: "Insert: Edit File"
date: 2022-04-07
draft: false
weight: 120
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-07 # UPDATE ANY TIME CHANGES ARE MADE
---

## Edit File

The most common way to edit the contents of a file is in `Insert` mode.

Enter `Insert` mode by typing `i` in `Normal` mode:

![alt-text](pictures/vim-insert.png?classes=border)

In `Insert` mode type your content:

![vim: content being added while in Insert mode](pictures/vim-insert-content.png?classes=border)

While in `Insert` mode your keyboard presses are redirected to the contents of the file.

## File Navigation in Insert Mode

While in `Insert` mode the cursor can be controlled with the directional arrow keys on your keyboard.

Try using the directional arrow keys to move your cursor over text. I will move the cursor after the period of the third paragraph:

![vim: insert mode cursor moved to end of third paragraph](pictures/vim-insert-move-cursor.png?classes=border)

After navigating to the new position you enter more text at the location of the cursor:

![alt-text](pictures/vim-insert-text-after-move.png?classes=border)

{{% notice note %}}
Navigation is possible in `Insert` mode, but is cumbersome. Luckily there are more effective ways to navigate the file while in `Normal` mode.
{{% /notice %}}

## Deleting Content in Insert Mode

While in `vim` Insert mode text can be deleted by using the `backspace` or `delete` keys. These keys behave the same way as they do in other text editors:

![alt-text](pictures/vim-insert-text-after-deletion.png?classes=border)