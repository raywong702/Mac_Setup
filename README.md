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
    devtoys \
    docker \
    flux \
    gitkraken \
    iterm2 \
    itsycal \
    latest \
    loom \
    microsoft-edge \
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
    font-meslo-lg-nerd-font \
    fzf \
    git \
    google-cloud-sdk \
    jq \
    k9s \
    kubernetes-cli \
    stow \
    vim \
    zsh \
    danielfoehrkn/switch/switch \
    rs/tap/curlie
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

Disable brew analytics in ~/.zshrc

```bash
echo "\n# brew" >> ~/.zshrc
echo 'export HOMEBREW_NO_ANALYTICS=1'  >> ~/.zshrc
```

## iTerm ##

```bash
# https://iterm2colorschemes.com
mkdir .iterm
THEME="OneHalfDark"
curl -sSL "https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/${THEME}.itermcolors" -o ~/.iterm/${THEME}.itermcolors
```

* In iTerm 2, go to Preferences->Profile>Text in your iTerm 2 preferences, then select Meslo LGS Nerd Font Mono in Font

* In Colors, choose Color Presets, choose Import, choose Theme you downloaded. May need to do Command + Shift + . to show hidden files. Choose Theme from Color Presets

* In Window, mkae transparency 57

* Navigate to profile > colors and make sure that the colors for Basic Colors > Background and ANSI Colors > Bright Black are different.

Background: 343a43
Black Normal: 090a0b
Black Bright: 1768f7

* In Terminal, choose Unlimited scrollback

* General->Closing Deselect Confirm boxes

## Zgenom and starter kit ##

```bash
cd ~
git clone https://github.com/jandamm/zgenom.git
git clone https://github.com/unixorn/zsh-quickstart-kit.git
cd zsh-quickstart-kit
stow --target="$HOME" zsh
```

Restart iTerm

Disable printing current ssh. Stop instant prompt verbose warning

```bash
zqs disable-ssh-key-listing
```

## powerlevel10k ##

```bash
p10k configure
```

* `n` - Use the current font
* `y` - Looks like a diamond
* `y` - Looks like a lock
* `y` - Looks like a debian logo
* `y` - Icons fit between X
* `1` - Lean
* `1` - Unicode
* `1` - 256 Colors
* `2` - 24 Hour Format
* `2` - 2 Lines
* `1` - Disconnected
* `1` - No frame
* `2` - Sparse
* `1` - Few icons
* `1` - Concise
* `y` - Enable Transient Prompt
* `1` - Verbose Instant Prompt

## asdf ##

```bash
echo "\n# asdf" >> ~/.zshrc
echo '. /opt/homebrew/opt/asdf/libexec/asdf.sh' >> ~/.zshrc
```

```bash
asdf plugin add istioctl
asdf install istioctl 1.10.6
asdf global istioctl 1.10.6

asdf plugin add terraform
asdf install terraform latest
asdf global terraform latest
```

## gcloud ##

```bash
echo "\n# gcloud" >> ~/.zshrc
echo 'source "/opt/homebrew/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/path.zsh.inc"' >> ~/.zshrc

gcloud components install gke-gcloud-auth-plugin

gcloud auth login

gcloud auth configure-docker
```

## kube-context ##

Comment out in ~/.p10k.zsh

```bash
# typeset -g POWERLEVEL9K_KUBECONTEXT_SHOW_ON_COMMAND='kubectl|helm|kubens|kubectx|oc|istioctl|kogito|k9s|helmfile|flux|fluxctl|stern|kubeseal|skaffold|kubent'
```

Update in ~/.p10k.zsh

```bash
typeset -g POWERLEVEL9K_KUBECONTEXT_DEFAULT_CONTENT_EXPANSION+='${P9K_KUBECONTEXT_CLOUD_ACCOUNT}-${P9K_KUBECONTEXT_CLOUD_CLUSTER:-${P9K_KUBECONTEXT_NAME}'
```

## kubeswitch ##

```bash
echo "\n# kubeswitch" >> ~/.zshrc
echo 'INSTALLATION_PATH=$(brew --prefix switch) && source $INSTALLATION_PATH/switch.sh' >> ~/.zshrc
```

## drivers ##

* https://www.synaptics.com/products/displaylink-graphics/downloads/macos
* https://www.logitech.com/en-us/software/logi-options-plus.html

## logioptions ##

Scrolling speed: 90%
Scroll direction: standard
Smooth scrolling: enabled
Free spin: enabled
Pointer speed: 80%

## vpn ##

* remoteaccess.forbes.com




## References ##

* https://github.com/unixorn/zsh-quickstart-kit
* https://github.com/ryanoasis/nerd-fonts#option-4-homebrew-fonts
* https://github.com/romkatv/powerlevel10k
* https://asdf-vm.com/guide/getting-started.html
* https://iterm2colorschemes.com
* https://github.com/danielfoehrKn/kubeswitch