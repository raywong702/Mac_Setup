# Mac Setup #

## Brew ##

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
echo >> /Users/rwong/.zprofile
```

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> /Users/rwong/.zprofile
```

```bash
eval "$(/opt/homebrew/bin/brew shellenv zsh)"
```

```bash
brew analytics off
brew update
brew doctor
```

## Brew Cask ##

```bash
brew tap \
  vmware-tanzu/carvel
```

```bash
brew install --cask \
    alfred \
    android-commandlinetools \
    android-file-transfer \
    appcleaner \
    bartender \
    caffeine \
    castctl \
    devtoys \
    docker \
    firefox \
    flux-app \
    font-hack-nerd-font \
    font-meslo-lg-nerd-font \
    gcloud-cli \
    gitkraken \
    google-cloud-sdk \
    iterm2 \
    itsycal \
    latest \
    loom \
    microsoft-edge \
    obsidian \
    orbstack \
    pgadmin4 \
    postman \
    raycast \
    realnvnc-connect-viewer \
    rectangle \
    shottr \
    spotify \
    spotmenu \
    sublime-text \
    tailscale-app \
    the-unarchiver \
    tealdeer \
    visual-studio-code \
    vnc-viewer \
    wireshark-app \
    zed \
    lingrino/tap/vaku
```

## Brew Install ##

```
brew trust danielfoehrkn/switch
```

```bash
brew install \
    argo \
    argocd \
    argocd-vault-plugin \
    awscli \
    bash \
    bat \
    container-diff \
    coreutils \
    crane \
    curlie \
    dive \
    eza \
    fastlane \
    fastly \
    font-meslo-lg-nerd-font \
    fd \
    findutils \
    fzf \
    gh \
    git \
    git-delta \
    git-filter-repo
    go \
    google-cloud-sdk \
    goreleaser \
    helm \
    jfrog-cli \
    jq \
    k3d \
    k9s \
    kube-capacity \
    kubecolor \
    kubent \
    kubernetes-cli \
    kustomize \
    mise \
    mongoose \
    neovim \
    npm \
    pluto \
    ripgrep \
    stern \
    stow \
    swiftformat \
    swiftlint \
    switch \
    tealdeer \
    terminal-notifier \
    thefuck \
    tree \
    tree-sitter-cli \
    vaku \
    vendir \
    vim \
    yq \
    ytt \
    zoxide \
    zsh \
    zstd \
    danielfoehrkn/switch/switch \
    lingrino/tap/vaku \
    rs/tap/curlie
```

```
==> Caveats
zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
zsh completions and functions have been installed to:
  /opt/homebrew/share/zsh/site-functions
==> bash
DEFAULT_LOADABLE_BUILTINS_PATH: /opt/homebrew/lib/bash:/usr/local/lib/bash:/usr/lib/bash:/opt/local/lib/bash:/usr/pkg/lib/bash:/opt/pkg/lib/bash:.
==> coreutils
Commands also provided by macOS and the commands dir, dircolors, vdir have been installed with the prefix "g".
If you need to use these commands with their normal names, you can add a "gnubin" directory to your PATH with:
  PATH="/opt/homebrew/opt/coreutils/libexec/gnubin:$PATH"
==> fzf
To set up shell integration, see:
  https://github.com/junegunn/fzf#setting-up-shell-integration
To use fzf in Vim, add the following line to your .vimrc:
  set rtp+=/opt/homebrew/opt/fzf
==> git
The Tcl/Tk GUIs (e.g. gitk, git-gui) are now in the `git-gui` formula.
Subversion interoperability (git-svn) is now in the `git-svn` formula.
==> mise
If you are using fish shell, mise will be activated for you automatically.
==> node
Single Executable Application is disabled as it doesn't work with shared libnode.
==> thefuck
Add the following to your .bash_profile, .bashrc or .zshrc:

  eval $(thefuck --alias)

For other shells, check https://github.com/nvbn/thefuck/wiki/Shell-aliases
==> vim
Additional features can be enabled by installing: lua, python@3.15, ruby
```

```bash
brew install \
  bash \
  coreutils \
  findutils \
  gnu-tar \
  gnu-sed \
  gawk \
  gnutls \
  gnu-indent \
  gnu-getopt \
  grep
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
echo 'export HOMEBREW_NO_ASK=1' >> ~/.zshrc
```

```bash
echo "\n# GNU" >> ~/.zshrc
echo 'export PATH="$(brew --prefix)/opt/coreutils/libexec/gnubin:$PATH"' >> ~/.zshrc
echo 'export PATH="$(brew --prefix)/opt/findutils/libexec/gnubin:$PATH"' >> ~/.zshrc
echo 'export PATH="$(brew --prefix)/opt/gnu-tar/libexec/gnubin:$PATH"' >> ~/.zshrc
echo 'export PATH="$(brew --prefix)/opt/gnu-sed/libexec/gnubin:$PATH"' >> ~/.zshrc
echo 'export PATH="$(brew --prefix)/opt/gnu-indent/libexec/gnubin:$PATH"' >> ~/.zshrc

# echo "\n# MANPATH" >> ~/.zshrc
# echo 'export MANPATH="$(brew --prefix)/opt/coreutils/libexec/gnuman:MANPATH"' >> ~/.zshrc
# echo 'export MANPATH="$(brew --prefix)/opt/findutils/libexec/gnuman:MANPATH"' >> ~/.zshrc
# echo 'export MANPATH="$(brew --prefix)/opt/gnu-tar/libexec/gnuman:MANPATH"' >> ~/.zshrc
# echo 'export MANPATH="$(brew --prefix)/opt/gnu-sed/libexec/gnuman:MANPATH"' >> ~/.zshrc
# echo 'export MANPATH="$(brew --prefix)/opt/gnu-indent/libexec/gnuman:$MANPATH"' >> ~/.zshrc
```

## iTerm ##

```bash
# https://iterm2colorschemes.com
mkdir .iterm
THEME="OneHalfDark"
curl -sSL "https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/refs/heads/master/schemes/One%20Half%20Dark.itermcolors" -o ~/.iterm/${THEME}.itermcolors
```

* In iTerm 2, go to Preferences->Profile>Text in your iTerm 2 preferences, then select Meslo LGS Nerd Font Mono in Font

* In Colors, choose Color Presets, choose Import, choose Theme you downloaded. May need to do Command + Shift + . to show hidden files. Choose Theme from Color Presets

* In Keys, choose Left Option key to be Esc+

* In Window, make transparency 57

* Navigate to profile > colors and make sure that the colors for Basic Colors > Background and ANSI Colors > Bright Black are different.

```
Background: 343a43
Black Normal: 090a0b
Black Bright: 1768f7
```

* In Terminal, choose Unlimited scrollback

* General->Closing Deselect Confirm boxes

## Zgenom and starter kit ##

```bash
cd ~
git clone https://github.com/unixorn/zsh-quickstart-kit.git
cd zsh-quickstart-kit
./bootsrap-zsh-quickstart-kit
```

Restart iTerm

```bash
# Disable printing current ssh. Stop instant prompt verbose warning
zqs disable-ssh-key-listing

# Enable oh my zsh plugins
zqs enable-omz-plugins

# Update visual to nvim
curl -fsSL https://raw.githubusercontent.com/raywong702/Mac_Setup/master/001-nvim -o ~/.zshrc.d/001-nvim
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

## thefuck ##

```bash
echo "\n# thefuck" >> ~/.zshrc
echo 'eval $(thefuck --alias)' >> ~/.zshrc
```

## tealdeer / tldr ##

```bash
tldr --update
```

## vault ##

```bash
echo "\n# vault" >> ~/.zshrc
echo 'export VAULT_ADDR=https://vault.forbes.com' >> ~/.zshrc
```

## fastlane

```bash
echo "\n# Fastlane" >> ~/.zshrc
echo 'export LC_ALL=en_US.UTF-8' >> ~/.zshrc
echo 'export LANG=en_US.UTF-8' >> ~/.zshrc
```

## docker

```bash
echo "\n# docker" >> ~/.zshrc
echo 'export DOCKER_DEFAULT_PLATFORM=linux/amd64' >> ~/.zshrc
```

## zoxide

```bash
echo "\n# zoxide" >> ~/.zshrc
echo 'eval "$(zoxide init zsh)"' >> ~/.zshrc
```

## Fastlane

```bash
echo "\n# Fastlane" >> ~/.zshrc
echo "LC_ALL=en_US.UTF-8" >> ~/.zshrc
echo "LANG=en_US.UTF-8" >> ~/.zshrc
```

## zoxcide

```bash
echo "\n# zoxide" >> ~/.zshrc
echo '"$(zoxide init zsh)"' >> ~/.zshrc
```

## go

```bash
echo "\n# go" >> ~/.zshrc
echo "PATH=~/go/bin:${PATH}" >> ~/.zshrc
```

## android

```bash
echo "\n# android" >> ~/.zshrc
echo "export ANDROID_HOME=/opt/homebrew/share/android-commandlinetools" >> ~/.zshrc
echo 'export PATH="/opt/homebrew/share/android-commandlinetools/platform-tools:/opt/homebrew/share/android-commandlinetools/emulator:$PATH"' >> ~/.zshrc
```

## kubecolor

```bash
echo "\n# kubecolor" >> ~/.zshrc
echo "kubectl="kubecolor"" >> ~/.zshrc
```

## mise

```bash
echo "\n# mise" >> ~/.zshrc
echo 'eval "$(mise activate zsh)"' >> ~/.zshrc
```

## gitkraken

```bash
echo "\n# gitkraken" >> ~/.zshrc
echo 'alias kraken="open gitkraken://repo/$(pwd)"' >> ~/.zshrc
```

## cloud auth

```bash
echo "\n# cloud auth" >> ~/.zshrc
echo 'preexec() {' >> ~/.zshrc
echo '    if [[ "$(gcloud auth print-identity-token 2>/dev/null)" == "" ]]' >> ~/.zshrc
echo '    then' >> ~/.zshrc
echo '        open -n -a "Firefox"' >> ~/.zshrc
echo '        gcloud auth login --update-adc' >> ~/.zshrc
echo '    fi' >> ~/.zshrc
echo '}' >> ~/.zshrc
```

## libpq

```bash
echo "\n# libpq" >> ~/.zshrc
echo 'export PATH="/opt/homebrew/opt/libpq/bin:$PATH"' >> ~/.zshrc
```

## krew

```bash
echo "\n# krew" >> ~/.zshrc
echo 'export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"' >> ~/.zshrc
```

## nvm

```bash
echo "\n# nvm" >> ~/.zshrc
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh" # This loads nvm' >> ~/.zshrc
echo '[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" # This loads nvm bash_completion' >> ~/.zshrc
```

## k9s

```bash
curl -fsSL https://raw.githubusercontent.com/derailed/k9s/refs/heads/master/skins/dracula.yaml \
  -o ~/Library/"Application Support"/k9s/skins/dracula.yaml
```

```bash
echo "\n# k9s" >> ~/.zshrc
echo 'export K9S_SKIN="dracula"' >> ~/.zshrc
```

## git global config ##

```bash
git config --global user.name "FIRST_NAME LAST_NAME"
git config --global user.email "MY_NAME@example.com"
```

## git auto setup remote ##

```bash
git config --global --add --bool push.autoSetupRemote true
```

## global git ignore ##

```bash
# global git ignore
git config --global core.excludesfile ~/.gitignore_global

curl -fsSL https://raw.githubusercontent.com/raywong702/Mac_Setup/master/.gitignore_global -o ~/.gitignore_global
```

## global git config ##

```bash
curl -fsSL https://raw.githubusercontent.com/dandavison/delta/main/themes.gitconfig -o ~/delta-themes.gitconfig
```

```bash
cat <<EOF >> ~/.gitconfig
[credential "https://github.com"]
	helper =
	helper = !/opt/homebrew/bin/gh auth git-credential
[credential "https://gist.github.com"]
	helper =
	helper = !/opt/homebrew/bin/gh auth git-credential
[color]
	ui = auto


# clearly makes git better

[column]
        ui = auto
[branch]
        sort = -committerdate
[tag]
        sort = version:refname
[init]
        defaultBranch = main
[diff]
        algorithm = histogram
        colorMoved = plain
        mnemonicPrefix = true
        renames = true
[push]
        default = simple
        autoSetupRemote = true
        followTags = true
[fetch]
        prune = true
        pruneTags = true
        all = true

# why the hell not?

[help]
        autocorrect = prompt
[commit]
        verbose = true
[rerere]
        enabled = true
        autoupdate = true
[core]
        excludesfile = ~/.gitignore
[rebase]
        autoSquash = true
        autoStash = true
        updateRefs = true

# a matter of taste (uncomment if you dare)

[core]
        # fsmonitor = true
        # untrackedCache = true
[merge]
        # (just 'diff3' if git version < 2.3)
        # conflictstyle = zdiff3
[pull]
        # rebase = true

# delta

[delta]
        features = "Dracula"
[include]
        path = ~/delta-themes.gitconfig
EOF
```

## nvim ##

```bash
mkdir -p ~/.config/nvim
cd ~/.config/nvim
git clone https://github.com/nvim-lua/kickstart.nvim.git .
cd -
nvim
```

## mason ##

Installed (13)

* autoflake
* autopep8
* beautysh
* gitlint
* gofumpt
* golangci-lint-langserver
* gopls
* lua-language-server
* prettier
* pylint
* terraform-ls
* tflint
* yaml-language-server
* yamlfmt
* yamllint

## nvim mason and lazy updates ##

```bash
vi
:Mason
U
:q!
:Lazy
U
:q!
```

## docker ##

* settings > general
* Start Docker Desktop when you log in
* Disable Send usage statistics
* Disable Show weekly tips
* settings > docker engine append

```bash
,
  "max-concurrent-downloads": 50,
  "max-concurrent-uploads": 50
```

## drivers ##

* https://www.synaptics.com/products/displaylink-graphics/downloads/macos
* https://www.logitech.com/en-us/software/logi-options-plus.html
* https://www.logitech.com/en-us/business/video-collaboration/logi-tune

## logioptions ##

* Scrolling speed: 90%
* Scroll direction: standard
* Smooth scrolling: enabled
* Free spin: enabled
* Pointer speed: 80%
* Thumb wheel speed: 70%
* Thumb wheel direction: inverted

## vscode ##

Command + ,

* `terminal.integrated.font` and set to `MesloLGS Nerd Font Mono`
* `telemetry` and set to `off`
* `bracketPair` and select checkbox

Extensions

* Code Spell Checker
* CodeSnap
* Dev Containers
* Docker
* Docker DX
* GitHub Copilot
* GitHub Copilot Chat
* Go
* GitLens
* HashiCorp Terraform
* Markdown All in One
* Markdown Preview Enhanced
* markdownlint
* Peacock
* Prettier - Code formatter
* TODO Highlight
* Trailing Spaces
* VCL - Varnish Configuration Language
* vscode-icons
* YAML

Peacock Extension Settings

* Surprise Me on Startup

Profile Icon > Enable Settings Sync

## vpn ##

* remoteaccess.forbes.com

## neovim ##

```
:Lazy
:Mason
```

## References ##

* https://github.com/unixorn/zsh-quickstart-kit
* https://github.com/ryanoasis/nerd-fonts#option-4-homebrew-fonts
* https://github.com/romkatv/powerlevel10k
* https://asdf-vm.com/guide/getting-started.html
* https://iterm2colorschemes.com
* https://github.com/danielfoehrKn/kubeswitch
* https://github.com/mas-cli/mas#-homebrew-integration
* https://betterprogramming.pub/how-to-make-macos-command-utilities-compatible-with-gnu-core-utilities-87889b266f4b
* https://github.com/nvim-lua/kickstart.nvim
* https://blog.gitbutler.com/how-git-core-devs-configure-git/
* https://github.com/dandavison/delta
