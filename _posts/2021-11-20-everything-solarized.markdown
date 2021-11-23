---
layout: post
title: "Everything, Solarized"
categories: rice
---
#### Tmux
[seebi/tmux-colors-solarized] [Tmux]

#### (N)vim
[altercation/vim-colors-solarized] [(N)vim]

#### Alacritty
Copy the [color scheme] [Alacritty] into your `~/.config/alacritty/alacritty.yml` file

#### Xfce  
Add the [theme files] [GUI] to your ~/.local/share/themes directory
```
mkdir -p ~/.local/share/themes
cd ~/.local/share/themes
git clone --single-branch https://github.com/rtlewis88/rtl88-Themes.git --branch Solarized-Dark-gtk-theme-colorpack
mv rtl88-Themes/Solarized-* .
rm -rf rtl88-Themes
```
[Set the theme] [Xfce-Wiki] in the Window Manager Settings and in the Appearance Settings  

[Tmux]: https://github.com/seebi/tmux-colors-solarized/blob/e5e7b4f1af37f8f3fc81ca17eadee5ae5d82cd09/tmuxcolors-dark.conf
[(N)vim]: https://github.com/altercation/vim-colors-solarized
[Alacritty]: https://clcode.net/articles/color-schemes.md
[GUI]: https://github.com/rtlewis88/rtl88-Themes/tree/Solarized-Dark-gtk-theme-colorpack
[Xfce-Wiki]: https://wiki.xfce.org/howto/install_new_themes
