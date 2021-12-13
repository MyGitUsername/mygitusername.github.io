---
layout: post
title:  "Path Variable Pitfalls and Tips"
date:   2021-12-12
---
#### Pitfalls
1. Incorrect use of the [tilde expansion] [filename expansion].  

    - `export PATH=~/.dir:$PATH` expands to `/home/username/.dir`  
    - `export PATH="~/.dir"` expands to `~/.dir`  
    - `export PATH="$HOME/.dir"` expands to `/home/username/.dir`  
    - `export PATH=$HOME/.dir` expands to `/home/username/.dir`  
    <br />
2. Specifying the incorrect directory.  
    - N.B. The exact *parent* directory of desired executable must be specified --
    not the grandparent, great-grandparent, etc.  
    - For example, if you want to run the program `foo.sh` which lives in `/usr/bin/run/foo.sh`,
    add the `/usr/bin/run` directory to your path; having `/usr/bin` in your path is not 
    sufficient.

#### Tips
1. According to the [user guide] [Zsh User Guide, Ch. 2], set your path in `.zshenv`.  

2. Add `typeset -U path` to your `.zshenv` to *not* add duplicate entries to your path.  

3. Modify your path like `path=(~/bin ~/progs/bin $path)`.  
    - PATH and path both set the search path for commands. These two 
    variables are equivalent, except that one is a string and one is an array.
    If the user modifies PATH, the shell changes path as well, and vice versa. [^1]  


Additional Sources:  
* [Arch Wiki] [Arch Wiki]  
* [Zsh User Guide] [Zsh User Guide]  
* [Zsh Homepage] [Zsh Homepage]  
* [Relevant SO] [Relevant SO]  


[^1]: [An Introduction To The Zsh Shell: Shell Parameters]

[Arch Wiki]: https://wiki.archlinux.org/title/Zsh
[Zsh User Guide]: https://zsh.sourceforge.io/Guide/zshguide.html
[Zsh Homepage]: https://zsh.org
[Relevant SO]: https://unix.stackexchange.com/questions/71253/what-should-shouldnt-go-in-zshenv-zshrc-zlogin-zprofile-zlogout
[Zsh User Guide, Ch. 2]: https://zsh.sourceforge.io/Guide/zshguide02.html
[filename expansion]: https://zsh.sourceforge.io/Doc/Release/Expansion.html#Filename-Expansion
[An Introduction To The Zsh Shell: Shell Parameters]: https://zsh.sourceforge.io/Intro/intro_13.html#IDX162
