# chinstrap

PENGUIN build tool

```sh
Usage: chinstrap <mode> [<pkg>] [--opt <arg>]

  chroot                      Manage chroot
    -C, --chroot-dir <dir>    Path to chroot directory
    -m, --makepkg <file>      Path to makepkg config
    -p, --pacman <file>       Path to pacman config
    --create                  Create chroot environment
    --remove                  Remote chroot directory
    --update                  Manualy update chroot

  list                        List available packages
    -W, --working-dir <dir>   Path to working directory
    -a, --aur                 Filter AUR packages (slow)
    -b, --built               Filter built packages (really slow)
    -g, --git                 Filter git packages

  clone <pkg(s)>              Clone package(s) from AUR
    -W, --working-dir <dir>   Path to working directory
    -l, --pkg-list <file>     List of packages to work on

  build <pkg(s)>              Build package(s)
    -P, --push-dir <dir>      Path on remote host
    -W, --working-dir <dir>   Path to working directory
    -l, --pkg-list <file>     List of packages to work on
    --login <user@host>       Login for remote host
    --push                    Push package(s) to repo

  push  <pkg(s)>              Push package(s) to repo
    -P, --push-dir <dir>      Path on remote host
    -W, --working-dir <dir>   Path to working directory
    -l, --pkg-list <file>     List of packages to work on
    --login <user@host>       Login for remote host

```
