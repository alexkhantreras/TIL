# Bash

<br/> <br/>

## Bash vs zsh
The two shells are largely compatible but have some important differences. Since I don't do a lot of bash scripting I'm going to change the default to what I know - bash.

On Mac, the default is now zsh but it can be changed back to bash by

- opening a Terminal shell
- entering `chsh -s /bin/bash`
- closing the shell and starting another
- check the shell in use with `echo $SHELL`, which should return `/bin/bash` now

<br/> <br/>

## Dot Files
Bash has a few dot files that are important
- `.profile` is overwritten if a `.bash_profile` exists
- `.bash_profile` is executed for login shells. If you log in by sitting at the machine or via ssh then this file is executed to configure the shell before the command prompt is shown.
- `.bashrc` is executed for interactive non-login shells and performs the same actions.
- On Mac, Terminal opens a login shell every time, so .`bash_profile` is used.
