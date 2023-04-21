# Should I use `apt` or `apt-get`?

**TL;DR**: Use `apt` for interactive usage and `apt-get` for scripting.

`apt-get` is part of the suite of package management commands that was released with Debian and related distros from the 90s. It represents a set of low-level commands for package management. `apt` is a more user-friendly CLI alternative that simplifies using most of these commands and adds prettier output. In reality, `apt` uses all the various `apt-*` commands behind the scenes. It's worth noting that `apt` doesn't match all the features of the `apt-*` and there are subtle differences with some of the commands (see the [Command table comparision](#command-table-comparision) for more info).

In 90% of use cases, it's preferred to use and learn `apt` itself, especially when working with the terminal interactively. The main exceptions would be when working with older TTY-based interfaces or in the context of scripting where pretty output doesn't matter as much, in which `apt-get` and other `apt-*` utilities should be used instead.

## Command table comparision

| Main _apt_ Command | Equivalent _apt-\*_ command | Function of command                                  |
|--------------------|-----------------------------|------------------------------------------------------|
| apt install        | apt-get install             | Installs a package                                   |
| apt remove         | apt-get remove              | Removes a package                                    |
| apt purge          | apt-get purge               | Removes package with configuration                   |
| apt update         | apt-get update              | Refreshes repository index                           |
| apt upgrade        | apt-get upgrade             | Upgrades all upgradable packages                     |
| apt autoremove     | apt-get autoremove          | Removes unwanted packages                            |
| apt full-upgrade   | apt-get dist-upgrade        | Upgrades packages with auto-handling of dependencies |
| apt search         | apt-cache search            | Searches for the program                             |
| apt show           | apt-cache show              | Shows package details                                |

## Read more

If you want to read more, check this out: https://itsfoss.com/apt-vs-apt-get-difference/