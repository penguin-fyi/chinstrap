# chinstrap
`chinstrap` is a tool to retrieve, build, and publish [clean-chroot](https://wiki.archlinux.org/title/DeveloperWiki:Building_in_a_clean_chroot) packages for Arch Linux.

## Installation
#### Single-user
1. Clone repo
    ```bash
    git clone https://github.com/penguin-fyi/chinstrap && cd chinstrap
    ```
2. Install `chinstrap`
    ```bash
    install -Dm 755 chinstrap ~/bin/chinstrap
    ```

#### System-wide
1. Clone repo
    ```bash
    git clone https://github.com/penguin-fyi/chinstrap && cd chinstrap
    ```
2. Install `chinstrap`
    ```bash
    install -Dm 755 chinstrap /usr/bin/chinstrap`
    ```
3. Install `zsh` completions (optional)
    ```bash
    install -Dm 644 completions/_chinstrap /usr/share/zsh/site-functions/_chinstrap
    ```
4. Install `zsh` plugin (optional)
    ```bash
    install -Dm 644 plugins/chinstrap.plugin.zsh /usr/share/zsh/plugins/chinstrap/chinstrap.plugin.zsh
    ```

## Configuration
```bash
## directory containing pkgbuilds
build_dir="$HOME/pkgbuilds"
## directory containing chroot
chroot_dir="$build_dir/chroot"
## custom pacman.conf
pacman_conf="$build_dir/configs/pacman.conf"
## custom makepkg.conf
makepkg_conf="$build_dir/configs/makepkg.conf"
## base URL to AUR
aur_url="https://aur.archlinux.org"
## AUR RPC URL
aur_rpc="$aur_url/rpc?v=5&"
## GPG key to sign packages (required)
gpg_key="1234567890ABCDEF"
## login on remote host
repo_login="user@host.domain.tld"
## path on remote host
repo_dir="/srv/http/repo/penguin/x86_64"
## auto push on build
auto_sync=true
```

## Usage
```bash
Usage: chinstrap <command> [<pkg>] [--opt <arg>]

  env                         Manage chroot environment
    -C, --chroot-dir <dir>    Path to $chroot_dir
    -m, --makepkg <file>      Path to makepkg config
    -p, --pacman <file>       Path to pacman config
    --create                  Create chroot environment
    --remove                  Remove chroot environment
    --update                  Update chroot environment

  list                        List available packages
    -B, --build-dir <dir>     Path to $build_dir
    -a, --aur                 Filter AUR packages (slow)
    -b, --built               Filter built packages (really slow)
    -g, --git                 Filter git packages

  clone <pkg(s)>              Clone packages(s) from AUR
    -B, --build-dir <dir>     Path to $build_dir
    -l, --pkg-list <file>     Path to package list

  make <pkg(s)>               Build package(s)
    -B, --build-dir <dir>     Path to $build_dir
    -R, --repo-dir <dir>      Path to package repo
    -k, --gpg-key <file>      GPG key used to sign package(s)
    -l, --pkg-list <file>     Path to package list
    --login <user@host>       Login for repo (user@host)
    --sync                    Automatically sync package(s)

  sync <pkg(s)>               Sync package(s) to repo
    -B, --build-dir <dir>     Path to $build_dir
    -R, --repo-dir <dir>      Path to package repo
    -l, --pkg-list <file>     Path to package list
    --login <user@host>       Login for repo (user@host)

```

