# Setup Ubuntu

## Run Update command

To make sure the Packages and Repos available on your Linux WSL app are up to date

```bash
sudo apt update && sudo apt upgrade -y
```

## Install tools needed for Brew

There are few tools that we need to have on the system such as curl in order to download
and install HomeBrew on our WSL 1 or 2 Linux apps. Therefore run below command with sudo access.

```bash
sudo apt-get install build-essential curl file git -y
```

## Install the Package Manager Brew

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

### Mark sure brew can be used in zsh   

```bash
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/mjones/.zshrc
```
### Install oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### Install Powerlevel10 theme

```bash
brew install powerlevel10k                                                                                                                
echo "source $(brew --prefix)/share/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc
```

### Make zsh your default shell to zsh

use `which zsh` to find you zsh path and upate the accordingly

```bash
sudo usermod -s /home/linuxbrew/.linuxbrew/bin/zsh monte
```
