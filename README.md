# Shell-configs

My zsh setup.

- **zsh** with [zinit](https://github.com/zdharma-continuum/zinit) for plugins: syntax
  highlighting, autosuggestions, extra completions and fzf-tab, plus oh-my-zsh's git,
  sudo and archlinux snippets.
- **Prompt:** [oh-my-posh](https://ohmyposh.dev) with the
  [zen theme](https://github.com/dreamsofautonomy/zen-omp). Its colors are fixed, so the
  prompt stays the same whatever the terminal's color scheme is.
- **History and navigation:** [atuin](https://atuin.sh) for history search and
  [zoxide](https://github.com/ajeetdsouza/zoxide), which replaces `cd`.

| File | Goes to |
|---|---|
| `zshrc` | `~/.zshrc` |
| `ohmyposh/zen.toml` | `~/.config/ohmyposh/zen.toml` |

## Installation (Arch Linux)

1. Install the dependencies. oh-my-posh is in the AUR (shown here with `yay`):

   ```sh
   sudo pacman -S --needed zsh git fzf zoxide atuin neovim ttf-jetbrains-mono-nerd
   yay -S oh-my-posh
   ```

   The prompt's git icon needs a [Nerd Font](https://www.nerdfonts.com): set one in your
   terminal.

2. Copy the files:

   ```sh
   git clone https://github.com/GitHub-MrAnnonymus/Shell-configs.git
   cd Shell-configs
   cp zshrc ~/.zshrc
   mkdir -p ~/.config/ohmyposh
   cp ohmyposh/zen.toml ~/.config/ohmyposh/
   ```

   Back up your own `~/.zshrc` first if you have one.

3. Make zsh your login shell, then log out and back in:

   ```sh
   chsh -s /usr/bin/zsh
   ```

The first start of zsh downloads zinit and the plugins, which takes a few seconds. Later
starts are fast.

## Notes

- `vim` is an alias for `nvim`.
- The `command-not-found` snippet suggests a package for unknown commands if `pkgfile` is
  installed (`sudo pacman -S pkgfile && sudo pkgfile -u`).
- On macOS the zshrc picks up Homebrew automatically. Install the same tools with `brew`.

## License

[MIT](LICENSE). The prompt theme is based on
[dreamsofautonomy/zen-omp](https://github.com/dreamsofautonomy/zen-omp).
