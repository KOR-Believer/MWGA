# MWGA
Make Windows Great Again

## 1. Install Windows terminal
https://www.microsoft.com/ko-kr/p/windows-terminal/9n0dx20hk701?rtc=1&activetab=pivot:overviewtab
- changing shell color theme
  - https://windowsterminalthemes.dev/
  - https://popcorn16.tistory.com/118

## 2. Install WSL2
### in PowerShell
```PowerShell
# install wsl2
$ wsl --install

# To List Available WSL Linux Distros
$ wsl --list --online

# install Ubuntu 20.04
$ wsl --install -d Ubuntu-20.04
```

### 2.1. in Ubuntu 20.04
  - Changing starting directory to "/home/[username]" 
  - Install Linuxbrew
    ```zsh
    # update
    $ sudo apt update
    
    # Install tool require to setup Brew 
    $ sudo apt-get install build-essential curl file git
    
    # Install HomeBrew
    $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    
    # Add Homebrew to your system PATH
    $ test -d ~/.linuxbrew && eval $(~/.linuxbrew/bin/brew shellenv)
    $ test -d /home/linuxbrew/.linuxbrew && eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)
    $ test -r ~/.bash_profile && echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.bash_profile
    $ echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.profile
    $ echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.zshrc
    ```
## 3. Install Visual Studio Code
https://code.visualstudio.com/download
### 3.1. in Visual Studio Code
- install Remote - WSL https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl
- changing shell color theme https://glitchbone.github.io/vscode-base16-term/#/icy
