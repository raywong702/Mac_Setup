# Mac Setup #

## Brew ##

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/rwong/.zprofile
```

```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

```bash
brew analytics off
brew update
brew doctor
```

## Brew Cask ##

```bash
brew tap homebrew/cask-fonts
```

```bash
brew install --cask \
    alfred \
    android-file-transfer \
    bartender \
    docker \
    flux \
    gitkraken \
    iterm2 \
    itsycal \
    latest \
    loom \
    obsidian \
    postman \
    rectangle \
    spotify \
    spotmenu \
    sublime-text \
    the-unarchiver \
    visual-studio-code
```

## Brew Install ##

```bash
brew install \
    asdf \
    font-hack-nerd-font \
    fzf \
    stow \
    zsh
```

```
To use asdf, add the following line (or equivalent) to your shell profile
e.g. ~/.profile or ~/.zshrc:
  . /opt/homebrew/opt/asdf/libexec/asdf.sh
Restart your terminal for the settings to take effect.

zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
==> Summary
🍺  /opt/homebrew/Cellar/asdf/0.11.2: 173 files, 714.2KB
==> Running `brew cleanup asdf`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Pouring fzf--0.38.0.arm64_ventura.bottle.tar.gz
==> Caveats
To install useful keybindings and fuzzy completion:
  /opt/homebrew/opt/fzf/install

To use fzf in Vim, add the following line to your .vimrc:
  set rtp+=/opt/homebrew/opt/fzf
==> Summary
🍺  /opt/homebrew/Cellar/fzf/0.38.0: 17 files, 3.5MB
==> Running `brew cleanup fzf`...
==> Caveats
==> asdf
To use asdf, add the following line (or equivalent) to your shell profile
e.g. ~/.profile or ~/.zshrc:
  . /opt/homebrew/opt/asdf/libexec/asdf.sh
Restart your terminal for the settings to take effect.

zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
==> fzf
To install useful keybindings and fuzzy completion:
  /opt/homebrew/opt/fzf/install

To use fzf in Vim, add the following line to your .vimrc:
  set rtp+=/opt/homebrew/opt/fzf
```

## Post Brew ##

```bash
# setup brew zsh as default shell
sudo dscl . -create /Users/$USER UserShell /opt/homebrew/bin/zsh
```

## iTerm ##

* In iTerm 2, go to Preferences->Profile>Text in your iTerm 2 preferences, then select Hack Nerd Font in Font

* Select Use built-in-Powerline glyphs?

* In Terminal, choose Unlimited scrollback

## Zgenom and starter kit ##

```bash
cd ~
git clone https://github.com/jandamm/zgenom.git
git clone https://github.com/unixorn/zsh-quickstart-kit.git
cd zsh-quickstart-kit
stow --target="$HOME" zsh
```

Restart iTerm

## powerlevel10k ##

```bash
p10k configure
```

* `n` - Use the current font
* `y` - Looks like a diamond
* `y` - Looks like a lock
* `y` - Looks like a debian logo
* `n` - Icon overlaps over X
* `1` - Lean
* `1` - Unicode
* `1` - 256 Colors
* `2` - 24 Hour Format
* `2` - 2 Lines
* `1` - Disconnected
* `1` - No frame
* `1` - Sparse
* `1` - Few icons
* `1` - Concise
* `y` - Enable Transient Prompt
* `1` - Verbose Instant Prompt

## drivers ##

* https://www.synaptics.com/products/displaylink-graphics/downloads/macos



## References ##

* https://github.com/unixorn/zsh-quickstart-kit
* https://github.com/ryanoasis/nerd-fonts#option-4-homebrew-fonts
* https://github.com/romkatv/powerlevel10k
* https://asdf-vm.com/guide/getting-started.html