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
    $ sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
      libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
      xz-utils tk-dev
    
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
  - nameserver setting
    ```zsh
    $ sudo rm /etc/resolv.conf
    $ sudo bash -c 'echo "nameserver 1.1.1.1" > /etc/resolv.conf'
    $ sudo bash -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'
    $ sudo bash -c 'echo "nameserver 8.8.4.4" > /etc/resolv.conf'
    $ sudo bash -c 'echo "[network]" > /etc/wsl.conf'
    $ sudo bash -c 'echo "generateResolvConf = false" >> /etc/wsl.conf'
    $ sudo chattr +i /etc/resolv.conf
    ```
  - install `mysql@5.7` (local)
    ```zsh
    # install mysql@5.7 from brew
    $ brew install mysql@5.7
    
    # add PATH
    $ echo 'export PATH="/home/linuxbrew/.linuxbrew/opt/mysql@5.7/bin:$PATH"' >> ~/.zshrc
    
    $ mysql_secure_installation
      Would you like to setup VALIDATE PASSWORD plugin? Press y|Y for Yes, any other key for No: n
      New password: your_root_password
      Re-enter new password: your_root_password
      Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
      Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
      Remove test database and access to it? (Press y|Y for Yes, any other key for No) : n
      Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
      All done!
    
    # find my.cnf file
    $ mysql --verbose --help | grep my.cnf
      /etc/my.cnf /etc/mysql/my.cnf /home/linuxbrew/.linuxbrew/etc/my.cnf ~/.my.cnf
    
    # change bind-address 127.0.0.1 to 0.0.0.0 in my.cnf
    $ vi /home/linuxbrew/.linuxbrew/etc/my.cnf
      # Default Homebrew MySQL server config
      [mysqld]
      # Only allow connections from localhost
      bind-address = 0.0.0.0
    
    $ ifconfig
      eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.20.184.132 ... # HOST OS(WINDOWS) MYSQL ENDPOINT (for Mysql Workbench)
    $ mysql.server start
    $ mysql -u root -p
      Enter password: your_root_password
    
    Welcome to the MySQL monitor.  Commands end with ; or \g.
    Your MySQL connection id is 25
    Server version: 5.7.37 Homebrew

    Copyright (c) 2000, 2022, Oracle and/or its affiliates.

    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners.

    Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

    mysql>
    ```
## 4. Install Visual Studio Code
https://code.visualstudio.com/download
### 4.1. in Visual Studio Code
- install Remote - WSL https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl
- changing shell color theme https://glitchbone.github.io/vscode-base16-term/#/icy
