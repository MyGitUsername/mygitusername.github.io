---
layout: post
title:  "Copy and Paste in Vim"
date:   2021-11-18
---
vim copy and paste

yank line into a particular register
in this case the register x
["x]yy

paste from register x
["x]p

paste from register y
["y]p

paste from the system clipboard
"+p

paste from register y
["y]p
paste from the system clipboard
"+p

pasting with `p` seems to paste the selection yanked
regardless of to which register
