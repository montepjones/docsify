# Setup Ubuntu

## Run Update command

To make sure the Packages and Repos available on your Linux WSL app are up to date

```bash
sudo apt update && sudo apt upgrade -y
```

### Install tools needed for Brew

There are few tools that we need to have on the system such as curl in order to download
and install HomeBrew on our WSL 1 or 2 Linux apps. Therefore run below command with sudo access.

```bash
sudo apt-get install build-essential curl file git -y
```

### Install the Package Manager Brew

Brew is a popular Mac package installer so why not use it on Ubuntu

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### add to .bashrc

```bash
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/mjones/.bashrc
```

### either close the terminal or run the below command

```bash
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

### Check the brew installation

```bash
brew doctor
```

### recommended to install wget gcc via brew

```bash
brew install gcc wget
```

## Install ZSH
 
 Install ZSH by running the below command

```bash
brew install zsh
```
### Make  sure brew can be used in zsh
```bash
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/mjones/.zshrc

```
### Install oh my posh
```bash
brew install jandedobbeleer/oh-my-posh/oh-my-posh
```
### install themem for oh my posh
```
(echo; echo 'eval "$(oh-my-posh init zsh --config $(brew --prefix oh-my-posh)/themes/jandedobbeleer.omp.json)"') >> /home/mjones/.zshrc
```

### setup zsh history  needs to be added to zshrc
```bash
# history setup
HISTFILE=$HOME/.zhistory
SAVEHIST=1000
HISTSIZE=999
setopt share_history
setopt hist_expire_dups_first
setopt hist_ignore_dups
setopt hist_verify

# setup  tab completion case insensitive
zstyle ':completion:*' matcher-list '' 'm:{a-zA-Z}={A-Za-z}' 'r:|=*' 'l:|=* r:|=*'
autoload -Uz compinit && compinit

# completion using arrow keys (based on history)
bindkey '^[[A' history-search-backward
bindkey '^[[B' history-search-forward
```
### setup zsh-autocomplettions
Install it. 
```bash
brew install zsh-autosuggestions
```
Then run the following:
```bash
echo "source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
```

### Setup zsh-syntax-highlighting
This will provide some really nice syntax highlighting as you type out commands.

Install it 
```bash
brew install zsh-syntax-highlighting
```
Then run:
```bash
echo "source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
```
