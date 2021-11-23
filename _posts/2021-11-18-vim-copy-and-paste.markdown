---
layout: post
title:  "Copy and Paste in Vim"
date:   2021-11-18
---
yank line into a particular register, in this case the register x
```
["x]yy
```

paste contents from register x
```
["x]p
```

paste contents from register y
```
["y]p
```

paste from the system clipboard
```
"+p
```

in vim command mode, try `:help p` for more information
