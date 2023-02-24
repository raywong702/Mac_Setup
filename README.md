# Mac Setup #

## Brew ##

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/raymond/.zprofile
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