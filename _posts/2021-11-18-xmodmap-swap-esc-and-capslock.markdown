---
layout: post
title:  "Modify Keyboard Layout in Linux"
date:   2021-11-18
---
I have an x230 laptop that I typically use docked on my desk to 
an external keyboard, the Kinesis Advantage 2.  

I've customized the Kinesis' layout with its [SmartSet 
Programming Engine] [Kinesis] to use more suitable keybindings. 

One of the customizations includes swapping the `capslock` and `esc` keys.
As an (n)vim user, I find the `esc` key is more often utilized than the `capslock` key, 
so it is ergonomically advantageous to swap the `esc` key to the default `capslock` 
location where the pinky can more easily reach it on the home row.

Unforunately, the keyboard layout customization does not persist when using the laptop's built-in
keyboard.  Here is how we can fix that, by persisting keymap modifications in Xorg, 
as explained in the hallowed [Arch wiki] [Arch-Wiki]:

> xmodmap is a utility for modifying keymaps and pointer button mappings in Xorg.

It is recommended for only simple keyboard modifications.

In `~/.xinitrc`, add the following line if you use GDM, XDM, or LightDM:
```
[[ -f ~/.Xmodmap ]] && xmodmap ~/.Xmodmap
```

Note: to confirm your display manager, run `systemctl status display-manager` (if 
your operating system uses systemd).


Source: [https://wiki.archlinux.org/title/Xmodmap] [Arch-Wiki]


[Arch-Wiki]: https://wiki.archlinux.org/title/Xmodmap
[Kinesis]: https://kinesis-ergo.com/shop/advantage2
