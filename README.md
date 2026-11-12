# Dotfiles

The dotfiles are managed by [GNU stow](https://www.gnu.org/software/stow/).
The manual is available
[here](https://www.gnu.org/software/stow/manual/stow.html#Invoking-Stow)

The sections below will explain how to store & restore configuration files.

## Storing configuration files

All the custom dotfiles are versioned in the `dotfiles` directory (usually
stored in `~/.git-repos/`).
The `dotfiles` directory may point to additional `git-modules` (e.g. `nvim`)
which have to be kept updated separately.
Each sub-directory inside the `dotfiles` directory refers to the program using
the configuration files stored in it.

> [!important]
>
> Dotfiles that starts with a dot `.`, have to be renamed with
> `dot-<file_name>`.
> E.g.:
> `.zshrc` -> `dot-zshrc`
>
> `stow` will take care of converting them in actual `.` once installed in the
> target directories.
> This avoids the result of having directories full of hidden files.

## Restoring configuration files

`cd` inside the `dotfiles` directory and invoke `stow` with the following
instruction:

```bash
stow --target=<target_dir> --dotfiles <program_name>
```

> [!note]
>
> usually \<`target_dir`> is `$HOME`.
