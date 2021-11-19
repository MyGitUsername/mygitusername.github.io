---
layout: post
title:  "Modify Keyboard Layout in Linux"
date:   2021-11-18
---
I have an x230 laptop that I typically use hooked up with an external 
monitor and external keyboard: a Kinesis Advantage 2.  I've customized the 
Kinesis' software to use more comfortable keybindings. 

One of the remappings includes swapping the capslock and esc key, 
as I often find myself reaching for `esc` as a (n)vim user.
However, the x230's keyboard mappings remain standard.   

Here is documentation copied from the hallowed Arch Linux wiki that shows
how to persist keymap modifications in Xorg.  This will help to acheive 
consistency when switching back in forth between my desktop and laptop
setups.

```
xmodmap is a utility for modifying keymaps and pointer button mappings in Xorg.
```

It is recommended for only simple keyboard modifications.

```
Activating the custom table

With GDM, XDM or LightDM there is no need to source ~/.Xmodmap. For startx, use:

~/.xinitrc

[[ -f ~/.Xmodmap ]] && xmodmap ~/.Xmodmap
```

To confirm the display manager, run `systemctl status display-manager` (if 
the system uses systemd).


Source:
https://wiki.archlinux.org/title/Xmodmap
