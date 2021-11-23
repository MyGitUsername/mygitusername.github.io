---
layout: post
title:  "dpkg"
---
To check if packagename was installed:
```
dpkg -s <packagename>
```

You can also use dpkg-query that has a neater output for your purpose, and accepts wild cards, too.
```
dpkg-query -l <packagename>
```

To find what package owns the command:
```
dpkg -S `which <command>`
```

Source: [Stack Overflow] 

[Stack Overflow]: https://stackoverflow.com/questions/1298066/how-can-i-check-if-a-package-is-installed-and-install-it-if-not
