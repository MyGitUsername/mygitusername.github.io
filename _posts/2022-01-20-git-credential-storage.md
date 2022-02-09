---
layout: post
title:  "Git Credential Storage for HTTPS Auth"
date:   2022-01-20
---
The git credentials system's default behavior is to prompt for a username and password
every connection when authenticating with HTTPS.  

Alternatives:
1. "cache" mode  -  Caches the password in memory; does not store on disk. The `--timeout <seconds>`
option changes the amount of time from the default 15 mins.    
  
2. "store" mode - Saves the credentials to the disk in plain-text.  The credentials
never expire. The default location is `~/.git-credentials`, but the command accepts
a `--file <path>` argument if a custom file path is desired.    
```
$ git config --global credential.helper 'store --file ~/.my-credentials'
```



Source: [Git-scm] [git-scm]

[git-scm]: https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage
