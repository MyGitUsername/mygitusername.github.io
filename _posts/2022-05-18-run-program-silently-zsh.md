---
layout: post
title:  "Run ZSH Command Silently"
date:   2022-05-18
---
```
>&| word
>&! word
&>| word
&>! word
```

Redirects both standard output and standard error (file descriptor 2) in the manner of \`>\| word\`.

For example, `./run-prog >&| /dev/null`

Source:
[ZSH Redirection](https://zsh.sourceforge.io/Doc/Release/Redirection.html)

