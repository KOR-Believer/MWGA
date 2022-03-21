# MWGA
> Make Windows Great Again!

## 1. Install PowerToys
- Download [From here](https://github.com/microsoft/PowerToys/releases).

## 2. Install Windows terminal
- Download [From here](https://www.microsoft.com/ko-kr/p/windows-terminal/9n0dx20hk701?rtc=1&activetab=pivot:overviewtab).

## 3. Install WSL2
- install WSL2 in PowerShell
  ```PowerShell
  # install wsl2
  $ wsl --install

  # To List Available WSL Linux Distros
  $ wsl --list --online

  # install Ubuntu 20.04
  $ wsl --install -d Ubuntu-20.04
  ```
### 3.1. in WSL2 Ubuntu 20.04
  - in Windows terminal Settings 
    - Changing starting directory to "/home/[username]" 
    - changing shell color theme
      - https://windowsterminalthemes.dev/
      - https://popcorn16.tistory.com/118


  - apt update
    ```bash
    $ sudo apt update
    ```
  - Install `zsh`
    ```zsh
    $ sudo apt install zsh
    ```
  - Install `oh-my-zsh`
    ```zsh
    $ sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
  - Install `Linuxbrew`
    ```zsh    
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
  - Install `pyenv`
    ```zsh
    # install from brew
    $ brew install pyenv
    
    # add pyenv to zsh
    $ echo -e "\n\n# pyenv environment variables\nexport PYENV_ROOT=\"\$HOME/.pyenv\"\nexport PATH=\"\$PYENV_ROOT/bin:\$PATH\"\n\n# pyenv initialization\nif command -v pyenv 1>/dev/null 2>&1; then\n  eval \"\$(pyenv init --path)\"\nfi\n\n" >> ~/.zshrc
    ```
  - Install `nvm`
    ```zsh
    # install script
    $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    
    # allow sudo at node and npm
    $ sudo ln -s "$NVM_DIR/versions/node/$(nvm version)/bin/node" "/usr/local/bin/node"
    $ sudo ln -s "$NVM_DIR/versions/node/$(nvm version)/bin/npm" "/usr/local/bin/npm"
    ```
## 4. Install Visual Studio Code
https://code.visualstudio.com/download
### 4.1. in Visual Studio Code
- install Remote - WSL https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl
- changing shell color theme https://glitchbone.github.io/vscode-base16-term/#/icy
