# Dotfiles repository

This repository contains configuration files and scripts to set up a consistent development environment across multiple devices.

## Setup

1. Clone the repository as a bare repository, allowing tracking of dotfiles without cluttering the home directory

   ```bash
   git clone --bare git@github.com:jerrypopsoff/dotfiles.git $HOME/.dotfiles
   ```

2. Define `config` as an alias for managing dotfiles in the home directory

   ```bash
   alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
   ```

   _Consider adding this alias to `.bashrc` or `.zshrc` for convenience._

3. Copy tracked dotfiles into the home directory. Be sure to backup any conflicting files before proceeding.

   ```bash
   config checkout
   ```

4. Hide untracked files in the home directory from `config status` output

   ```bash
   config config --local status.showUntrackedFiles no
   ```

## Managing dotfiles

To add or commit changes to the dotfiles, use the `config` alias:

```bash
config status
config add .vimrc
config commit -m "Update vimrc"
config push
```

## References

- [Awesome Dotfiles](https://github.com/webpro/awesome-dotfiles)
- [Unofficial dotfiles guide](https://dotfiles.github.io/)
- [Atlassian: Managing dotfiles](https://www.atlassian.com/git/tutorials/dotfiles)

## License

This repository is licensed under the [MIT License](LICENSE).
