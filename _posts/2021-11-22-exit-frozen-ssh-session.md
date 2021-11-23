---
layout: post
title: "Exit Frozen SSH Session"
---
1. terminate the connection with `~.`
2. kill the process that froze up `ssh -l $USER $HOSTNAME 'pkill -9 PNAME'`
3. try to ssh back into session
