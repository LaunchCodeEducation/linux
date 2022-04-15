---
title: "Changing Between Normal & Insert Modes"
date: 2022-04-07
draft: false
weight: 115
---

## Normal Mode to Insert Mode

Open `temp-file.txt`:

![vim temp-file.txt output](pictures/vim-temp-file.png?classes=border)

When opening a file, `vim` defaults to `Normal` mode. 

In `Normal` mode commands can be given to `vim`. When content needs to be added the easiest option is to change from `Normal` mode to `Insert` mode.

`Insert` mode will allow us to type directly into the file.

You can enter `Insert` mode from `Normal` mode by typing the `i` key:

![vim: i output](pictures/vim-insert.png?classes=border)

Note the text at the bottom of the terminal window changed to:

```bash
-- INSERT --
```

When **-- INSERT --** is seen at the bottom of the terminal window `vim` is in `Insert` mode.

{{% notice note %}}
While `vim` is in `Insert` mode text can be typed directly into the file. This will be demonstrated in the next article.
{{% /notice %}}

## Insert Mode to Normal Mode

While in `Insert` mode (and most other modes) you can return back to `Normal` mode by hitting the `escape` (`esc`) key on your keyboard.

Try it out and notice the change to the `vim` terminal window:

![vim: `esc` output](pictures/vim-esc.png?classes=border)

Take note of the bottom of the `vim` terminal window, it does display **-- INSERT --** any more indicating `vim` is back in `Normal` mode.

{{% notice warning %}}
There are **many** modes in `vim` and it's easy to wander into a mode you don't understand when you are learning `vim`. The `escape` key is the best way to return back to `Normal` mode while in another mode. The `escape` key will cancel any in progress commands. 

You may find yourself in an unfamiliar mode in the middle of a command, hitting `escape` will cancel the command, but you will need to hit `escape` again to return back to `Normal` mode. For this reason if you need to return back to `Normal` mode and are unsure of what's currently happening you can simply hit the `escape` key two or three times.
{{% /notice %}}