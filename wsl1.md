# WSL 1
## Install
Reference: https://docs.microsoft.com/en-us/windows/wsl/install-win10  
1. Enable Feature *Windows Subsystem for Linux* `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
2. Restart
3. [MANUAL Install Distribution of Choice](https://docs.microsoft.com/en-us/windows/wsl/install-manual)  
   --> **Ubuntu 20.04 LTS** (use curl to download)
4. Run Ubuntu 20.04 from Start Menu to setup account

## Setup Basics
1. Install tools
   1. Native
      ```bash
      # update package sources
      sudo apt-get update

      # upgrade installed packages
      sudo apt-get upgrade

      # install new packages
      sudo apt-get install \
      jq \
      git \
      python3-pip \
      npm \
      unzip

      # Install python packages
      python3 -m pip install \
      yq \
      ```
   2. Other vendors
      1. [GitHub CLI](https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian-ubuntu-linux-apt)
2. Fix file mode for mounted windows volumes:
   1. Add the following to `/etc/wsl.conf`; create file if not existend
      ```text
      [automount]
      enabled  = true
      root     = /mnt/
      options  = "metadata,umask=22,fmask=111"
      ```
   2. Restart WSL
      1. Close all wsl console windows
      2. Open cmd.exe as Administrator
      3. Shutdown WSL with `net stop LxssManager`
      4. Start WSL with `net start LxssManager`

## Tools
### Git
Create SSH Key and add to git services
```bash
# Create directory for key and link .ssh directory on Windows Filesystem to ~/.ssh
mkdir /mnt/c/Users/krsche/.ssh
ln -s /mnt/c/Users/krsche/.ssh ~/.ssh
chmod 700 ~/.ssh

# Create new ssh key (common for windows & linux)
ssh-keygen -t rsa -b 4096 -C "krsche@trixie" -f /mnt/c/Users/krsche/.ssh/id_rsa

# Add ssh-key to ssh-agent
eval $(ssh-agent)
ssh-add ~/.ssh/id_rsa

# Add public key to github (answer questions appropriatly; upload public-key; auth via browser)
gh auth login
```