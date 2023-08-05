# Terminal 101

- [OS History](https://eylenburg.github.io/os_familytree.htm)
- [1st Edition Unix Manual](https://www.bell-labs.com/usr/dmr/www/1stEdman.html) - November 3, 1971

## Shell

- `echo $SHELL` - to see current shell
- `chsh -s /bin/bash` - change shell to bash
- `chsh -s /bin/zsh` - change shell to zsh

_Restart terminal window_

# Commands

- `date` - current date
- `ncal` - calendar of month - vertical
- `cal` - calendar - horizontal
- `ncal <month> <year>` - specific cal

# Options

Generally written first in the command if an input is needed

- prefixed with `-`
- `date -u` : universal time

_example_

```
ncal -j
ncal -3
```

**Multiple Options**

_same meaning different syntax_

- `ncal -3 -h -j`
- `ncal -3h`

## Long form option

_Some commad options accept not all_

- prefixed with `--`

_same command_

- `date -u`
- `date --universal`

## Options with parameters

Requires an input to compute

- `ncal -A 5` : 5 months after current month
- `ncal -B 3` : 3 months before current month
