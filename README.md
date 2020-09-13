# LINUX
## Install VirtualBox Guest Additions
* [**CentOS 8**](https://www.tecmint.com/install-virtualbox-guest-additions-on-centos-8/)
* [**Ubuntu 20.4**](https://www.itzgeek.com/post/how-to-install-virtualbox-guest-additions-on-ubuntu-20-04/)
## Install Development Tools
**CentOS 8**
```shell 
sudo dnf groupinfo "Development Tools"
```
**Ununtu 20.4**
```shell
sudo apt install build-essential
```
## Install oh-my-zsh
### 1. Install git và zsh
**CentOS 8**
```shell
sudo dnf install zsh git
```
**Ununtu 20.4**
```shell
sudo apt install zsh git
```
## 2. Changing default shell from bash to zsh 
```shell
chsh -s /usr/bin/zsh
```
Logout, login back
### 3. Install oh-my-zsh and plugins
Oh-my-zsh
```shell
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Autosuggestions
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
Syntax-highlighting
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
History-substring-search
```shell
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
```
**Config**
<br>Edit file ```.zshrc```: Open terminal,  run ``` vim ~/.zshrc ```
<br>Insert plugins:  ```plugins=(git zsh-autosuggestions zsh-syntax-highlighting zsh-history-substring-search)```
<br>Config for each plugin
```
source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
ZSH_HIGHLIGHT_STYLES[default]=white
ZSH_HIGHLIGHT_STYLES[unknown-token]=fg=red,bold
ZSH_HIGHLIGHT_STYLES[reserved-word]=fg=red,bold,standout
ZSH_HIGHLIGHT_STYLES[alias]=fg=white,bold
ZSH_HIGHLIGHT_STYLES[builtin]=fg=white,bold
ZSH_HIGHLIGHT_STYLES[function]=fg=white,bold
ZSH_HIGHLIGHT_STYLES[command]=fg=white,bold
ZSH_HIGHLIGHT_STYLES[precommand]=fg=white,bold,underline
ZSH_HIGHLIGHT_STYLES[commandseparator]=none
ZSH_HIGHLIGHT_STYLES[hashed-command]=fg=009
ZSH_HIGHLIGHT_STYLES[path]=fg=214,underline
ZSH_HIGHLIGHT_STYLES[globbing]=fg=063
ZSH_HIGHLIGHT_STYLES[history-expansion]=fg=white,underline
ZSH_HIGHLIGHT_STYLES[single-hyphen-option]=none
ZSH_HIGHLIGHT_STYLES[double-hyphen-option]=none
ZSH_HIGHLIGHT_STYLES[back-quoted-argument]=none
ZSH_HIGHLIGHT_STYLES[single-quoted-argument]=fg=063,bold
ZSH_HIGHLIGHT_STYLES[double-quoted-argument]=fg=063,bold
ZSH_HIGHLIGHT_STYLES[dollar-double-quoted-argument]=fg=009
ZSH_HIGHLIGHT_STYLES[back-double-quoted-argument]=fg=009
ZSH_HIGHLIGHT_STYLES[assign]=none

source /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh
ZSH_AUTOSUGGEST_BUFFER_MAX_SIZE=20
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE=fg=246,underline

zmodload zsh/terminfo
bindkey "$terminfo[kcuu1]" history-substring-search-up
bindkey "$terminfo[kcud1]" history-substring-search-down
bindkey '^[[A' history-substring-search-up
bindkey '^[[B' history-substring-search-down
```